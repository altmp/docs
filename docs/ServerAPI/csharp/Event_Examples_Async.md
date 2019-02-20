## Event Examples



## OnCheckpoint

```csharp
private async Task OnCheckpoint(ICheckpoint checkpoint, IEntity entity, bool state)
{
	Position entityPosition = await entity.GetPositionAsync();
	Position checkPosition = await checkpoint.GetPositionAsync();

	if (state)
	{
		//Executed if entity enters checkpoint
		switch (entity.Type)
		{
			case EntityType.Player:
				AltAsync.Log("A player has entered the checkpoint: player-position "
						+ entityPosition + " - checkpoint-position "
						+ checkPosition);
				break;
			case EntityType.Vehicle:
				AltAsync.Log("A vehicle has entered the checkpoint: vehicle-position "
						+ entityPosition + " - checkpoint-position "
						+ checkPosition);
				break;
			default:
				AltAsync.Log("A entity has entered the checkpoint: entity-position "
						+ entityPosition + " - checkpoint-position "
						+ checkPosition);
				break;
		}
	}
	else
	{
		//Executed if entity leaves checkpoint
		switch (entity.Type)
		{
			case EntityType.Player:
				AltAsync.Log("A player has left the checkpoint: player-position "
						+ entityPosition + " - checkpoint-position "
						+ checkPosition);
				break;
			case EntityType.Vehicle:
				AltAsync.Log("A vehicle has left the checkpoint: vehicle-position "
						+ entityPosition + " - checkpoint-position "
						+ checkPosition);
				break;
			default:
				AltAsync.Log("A entity has left the checkpoint: entity-position "
						+ entityPosition + " - checkpoint-position "
						+ checkPosition);
				break;
		}
	}
}
```



## OnEntityRemove

```csharp
private async Task OnEntityRemove(IEntity entity)
{
	Position entityPosition = await entity.GetPositionAsync();
	
	switch (entity.Type)
	{
		case EntityType.Player:
			AltAsync.Log("A player has been removed, at position "
					+ entityPosition + ".");
			break;
		case EntityType.Vehicle:
			AltAsync.Log("A vehicle has been removed, at position "
					+ entityPosition + ".");
			break;
		case EntityType.Blip:
			AltAsync.Log("A blip has been removed, at position "
					+ entityPosition + ".");
			break;
		case EntityType.Checkpoint:
			AltAsync.Log("A checkpoint has been removed, at position "
					+ entityPosition + ".");
			break;
		default:
			AltAsync.Log("A entity has been removed, at position "
					+ entityPosition + ".");
			break;
	}
}
```



## OnPlayerConnect

```csharp
private async Task OnPlayerConnect(IPlayer player, string reason)
{
	string playerName = await player.GetNameAsync();

	AltAsync.Log(playerName + "has joined the server. (" + reason + ")");
}
```



## OnPlayerDamage

```csharp
private async Task OnPlayerDamage(IPlayer player, IEntity attacker, uint weapon,
	byte damage)
{
	string playerName = await player.GetNameAsync();

	switch (attacker.Type)
	{
		case EntityType.Player:
			var playerAttacker = (IPlayer)attacker;
			string playerAttackerName = await playerAttacker.GetNameAsync();

			AltAsync.Log(playerName + " has been damaged by " + playerAttackerName
					+ " with weapon " + weapon + " and suffered " + damage +
					" HP.");
			break;
		case EntityType.Vehicle:
			var vehicleAttacker = (IVehicle)attacker;
			IPlayer driver = await vehicleAttacker.GetDriverAsync();
			string driverName = await driver.GetNameAsync();

			AltAsync.Log(playerName + " has been damaged by a vehicle (Driver: "
								+ driverName + ") and suffered "
								+ damage + " HP.");
			break;
		default:
			AltAsync.Log(playerName + " has been damaged by an Entity and suffered "
								+ damage + ".");
			break;
	}
}
```



## OnPlayerDead

```csharp
private async Task OnPlayerDead(IPlayer player, IEntity killer, uint weapon)
{
	
	string playerName = await player.GetNameAsync();

	switch (killer.Type)
	{
		case EntityType.Player:
			IPlayer playerKiller = (IPlayer)killer;
			string playerKillerName = await playerKiller.GetNameAsync();

			AltAsync.Log(playerName + " has been killed by " + playerKillerName
								+ " with weapon " + weapon + ".");
			break;
		case EntityType.Vehicle:
			IVehicle vehicleKiller = (IVehicle)killer;
			IPlayer driver = await vehicleKiller.GetDriverAsync();
			string driverName = await driver.GetNameAsync();

			AltAsync.Log(playerName + " has been killed by a vehicle (Driver: "
								+ driverName + ").");
			break;
		default:

			AltAsync.Log(playerName + " has been killed by an Entity.");
			break;
	}
	
}
```



## OnPlayerDisconnect

```csharp
private async Task OnPlayerDisconnect(IPlayer player, string reason)
{
	string playerName = await player.GetNameAsync();

	AltAsync.Log(playerName + "has left the server. (" + reason + ")");
}
```



## OnVehicleChangeSeat

```csharp
private async Task OnVehicleChangeSeat(IVehicle vehicle, IPlayer player, sbyte oldSeat,
            sbyte newSeat)
{
	IPlayer driver = await vehicle.GetDriverAsync();
	string driverName = await driver.GetNameAsync();
	string playerName = await player.GetNameAsync();

	AltAsync.Log(playerName + " has changed seat in vehicle (Driver: "
						+ driverName + ") from " + oldSeat
						+ " to " + newSeat + ".");

}
```



## OnVehicleEnter

```csharp
private async Task OnVehicleEnter(IVehicle vehicle, IPlayer player, sbyte seat)
{
	IPlayer driver = await vehicle.GetDriverAsync();
	string driverName = await driver.GetNameAsync();
	string playerName = await player.GetNameAsync();

	AltAsync.Log(playerName + " entered vehicle (Driver: " + driverName 
						+ ") on seat " + seat + ".");

	await Task.Delay(5000);

	AltAsync.Log(playerName + " entered vehicle 5 seconds ago.");
}
```



## OnVehicleLeave

```csharp
private async Task OnVehicleLeave(IVehicle vehicle, IPlayer player, sbyte seat)
{
	IPlayer driver = await vehicle.GetDriverAsync();
	string driverName = await driver.GetNameAsync();
	string playerName = await player.GetNameAsync();

	AltAsync.Log(playerName + " left vehicle (Driver: " + driverName
						+ ") from seat " + seat + ".");
}
```



## Complete Example

```csharp
using System.Threading.Tasks;
using AltV.Net;
using AltV.Net.Async;
using AltV.Net.Data;
using AltV.Net.Elements.Entities;

namespace CSharp_Examples
{
    public class AsyncEvents : AsyncResource
    {
        public override void OnStart()
        {
            AltAsync.OnCheckpoint += OnCheckpoint;
            AltAsync.OnEntityRemove += OnEntityRemove;
            AltAsync.OnPlayerConnect += OnPlayerConnect;
            AltAsync.OnPlayerDamage += OnPlayerDamage;
            AltAsync.OnPlayerDead += OnPlayerDead;
            AltAsync.OnPlayerDisconnect += OnPlayerDisconnect;
            AltAsync.OnVehicleChangeSeat += OnVehicleChangeSeat;
            AltAsync.OnVehicleEnter += OnVehicleEnter;
            AltAsync.OnVehicleLeave += OnVehicleLeave;
            AltAsync.OnPlayerEvent += OnPlayerEvent;

            // Custom Event Triggers can be found at the bottom
            // Custom Event Type 01
            AltAsync.On("customEvent01", async args =>
            {
                await Task.Delay(1000);
                AltAsync.Log("customEvent01 triggered with following arguments: " + args[0]);
            });

            // Custom Event Type 02 - Fixed Argument Type
            AltAsync.On<string>("customEvent02", async str =>
            {
                await Task.Delay(1000);
                AltAsync.Log("customEvent01 triggered with following argument: " + str);
            });

            // Custom Event Type 03 - Delegate Type
            AltAsync.On("customEvent03", async delegate (string str)
            {
                await Task.Delay(1000);
                AltAsync.Log("customEvent03 triggered with following argument: " + str);
            });

            // Custom Event Type 04 - Method Call
            AltAsync.On<string>("customEvent04", CustomEvent04);

            AltAsync.Log("Resource \"CSharp_Examples\" has been started.");
        }

        private async Task OnCheckpoint(ICheckpoint checkpoint, IEntity entity, bool state)
        {
            Position entityPosition = await entity.GetPositionAsync();
            Position checkPosition = await checkpoint.GetPositionAsync();

            if (state)
            {
                //Executed if entity enters checkpoint
                switch (entity.Type)
                {
                    case EntityType.Player:
                        AltAsync.Log("A player has entered the checkpoint: player-position "
                                + entityPosition + " - checkpoint-position "
                                + checkPosition);
                        break;
                    case EntityType.Vehicle:
                        AltAsync.Log("A vehicle has entered the checkpoint: vehicle-position "
                                + entityPosition + " - checkpoint-position "
                                + checkPosition);
                        break;
                    default:
                        AltAsync.Log("A entity has entered the checkpoint: entity-position "
                                + entityPosition + " - checkpoint-position "
                                + checkPosition);
                        break;
                }
            }
            else
            {
                //Executed if entity leaves checkpoint
                switch (entity.Type)
                {
                    case EntityType.Player:
                        AltAsync.Log("A player has left the checkpoint: player-position "
                                + entityPosition + " - checkpoint-position "
                                + checkPosition);
                        break;
                    case EntityType.Vehicle:
                        AltAsync.Log("A vehicle has left the checkpoint: vehicle-position "
                                + entityPosition + " - checkpoint-position "
                                + checkPosition);
                        break;
                    default:
                        AltAsync.Log("A entity has left the checkpoint: entity-position "
                                + entityPosition + " - checkpoint-position "
                                + checkPosition);
                        break;
                }
            }
        }

        private async Task OnEntityRemove(IEntity entity)
        {
            Position entityPosition = await entity.GetPositionAsync();

            switch (entity.Type)
            {
                case EntityType.Player:
                    AltAsync.Log("A player has been removed, at position "
                            + entityPosition + ".");
                    break;
                case EntityType.Vehicle:
                    AltAsync.Log("A vehicle has been removed, at position "
                            + entityPosition + ".");
                    break;
                case EntityType.Blip:
                    AltAsync.Log("A blip has been removed, at position "
                            + entityPosition + ".");
                    break;
                case EntityType.Checkpoint:
                    AltAsync.Log("A checkpoint has been removed, at position "
                            + entityPosition + ".");
                    break;
                default:
                    AltAsync.Log("A entity has been removed, at position "
                            + entityPosition + ".");
                    break;
            }
        }


        private async Task OnPlayerConnect(IPlayer player, string reason)
        {
            string playerName = await player.GetNameAsync();

            AltAsync.Log(playerName + "has joined the server. (" + reason + ")");
        }

        private async Task OnPlayerDamage(IPlayer player, IEntity attacker, uint weapon,
            byte damage)
        {
            string playerName = await player.GetNameAsync();

            switch (attacker.Type)
            {
                case EntityType.Player:
                    var playerAttacker = (IPlayer)attacker;
                    string playerAttackerName = await playerAttacker.GetNameAsync();

                    AltAsync.Log(playerName + " has been damaged by " + playerAttackerName
                            + " with weapon " + weapon + " and suffered " + damage +
                            " HP.");
                    break;
                case EntityType.Vehicle:
                    var vehicleAttacker = (IVehicle)attacker;
                    IPlayer driver = await vehicleAttacker.GetDriverAsync();
                    string driverName = await driver.GetNameAsync();

                    AltAsync.Log(playerName + " has been damaged by a vehicle (Driver: "
                                        + driverName + ") and suffered "
                                        + damage + " HP.");
                    break;
                default:
                    AltAsync.Log(playerName + " has been damaged by an Entity and suffered "
                                        + damage + ".");
                    break;
            }
        }

        private async Task OnPlayerDead(IPlayer player, IEntity killer, uint weapon)
        {
            
            string playerName = await player.GetNameAsync();

            switch (killer.Type)
            {
                case EntityType.Player:
                    IPlayer playerKiller = (IPlayer)killer;
                    string playerKillerName = await playerKiller.GetNameAsync();

                    AltAsync.Log(playerName + " has been killed by " + playerKillerName
                                        + " with weapon " + weapon + ".");
                    break;
                case EntityType.Vehicle:
                    IVehicle vehicleKiller = (IVehicle)killer;
                    IPlayer driver = await vehicleKiller.GetDriverAsync();
                    string driverName = await driver.GetNameAsync();

                    AltAsync.Log(playerName + " has been killed by a vehicle (Driver: "
                                        + driverName + ").");
                    break;
                default:

                    AltAsync.Log(playerName + " has been killed by an Entity.");
                    break;
            }
            
        }

        private async Task OnPlayerDisconnect(IPlayer player, string reason)
        {
            string playerName = await player.GetNameAsync();

            AltAsync.Log(playerName + "has left the server. (" + reason + ")");
        }

        private async Task OnVehicleChangeSeat(IVehicle vehicle, IPlayer player, sbyte oldSeat,
            sbyte newSeat)
        {
            IPlayer driver = await vehicle.GetDriverAsync();
            string driverName = await driver.GetNameAsync();
            string playerName = await player.GetNameAsync();

            AltAsync.Log(playerName + " has changed seat in vehicle (Driver: "
                                + driverName + ") from " + oldSeat
                                + " to " + newSeat + ".");

        }

        private async Task OnVehicleEnter(IVehicle vehicle, IPlayer player, sbyte seat)
        {
            IPlayer driver = await vehicle.GetDriverAsync();
            string driverName = await driver.GetNameAsync();
            string playerName = await player.GetNameAsync();

            AltAsync.Log(playerName + " entered vehicle (Driver: " + driverName 
                                + ") on seat " + seat + ".");

            await Task.Delay(5000);

            AltAsync.Log(playerName + " entered vehicle 5 seconds ago.");
        }

        private async Task OnVehicleLeave(IVehicle vehicle, IPlayer player, sbyte seat)
        {
            IPlayer driver = await vehicle.GetDriverAsync();
            string driverName = await driver.GetNameAsync();
            string playerName = await player.GetNameAsync();

            AltAsync.Log(playerName + " left vehicle (Driver: " + driverName
                                + ") from seat " + seat + ".");
        }

        public override void OnStop()
        {
            AltAsync.Log("Resource \"CSharp_Examples\" has been stopped.");
        }

        private void TriggerCustomEvents()
        {
            // All Custom Events are called the same way.
            Alt.Emit("customEvent01", "FooBar");
            Alt.Emit("customEvent02", "FooBar");
            Alt.Emit("customEvent03", "FooBar");
            Alt.Emit("customEvent04", "FooBar");
        }

        public void CustomEvent04(string str)
        {
            AltAsync.Log("customEvent04 triggered with following argument: " + str);
        }

        // Can been triggered from a Client Event
        private async Task OnPlayerEvent(IPlayer player, string eventName, object[] args)
        {
            string playerName = await player.GetNameAsync();

            switch (eventName)
            {
                case "playerEventA":
                {
                    AltAsync.Log(playerName + " has triggered Event A, "
                                        + "with following Args:");
                    foreach (var arg in args)
                    {
                        AltAsync.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
                case "playerEventB":
                {
                    AltAsync.Log(playerName + " has triggered Event B, "
                                        + "with following Args:");
                    foreach (var arg in args)
                    {
                        AltAsync.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
            }

        }
    }
}
```
