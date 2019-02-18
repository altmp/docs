## Event Examples



## OnCheckpoint

```csharp
private Task OnCheckpoint(ICheckpoint checkpoint, IEntity entity, bool state)
{
	if (state)
	{
		//Executed if entity enters checkpoint
		switch (entity.Type)
		{
			case EntityType.Player:
				AltAsync.Log("A player has entered the checkpoint: player-position "
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
				break;
			case EntityType.Vehicle:
				AltAsync.Log("A vehicle has entered the checkpoint: vehicle-position "
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
				break;
			default:
				AltAsync.Log("A entity has entered the checkpoint: entity-position "
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
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
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
				break;
			case EntityType.Vehicle:
				AltAsync.Log("A vehicle has left the checkpoint: vehicle-position "
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
				break;
			default:
				AltAsync.Log("A entity has left the checkpoint: entity-position "
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
				break;
		}
	}

	return Task.CompletedTask;
}
```



## OnEntityRemove

```csharp
private Task OnEntityRemove(IEntity entity)
{
	switch (entity.Type)
	{
		case EntityType.Player:
			AltAsync.Log("A player has been removed, at position "
					+ entity.Position + ".");
			break;
		case EntityType.Vehicle:
			AltAsync.Log("A vehicle has been removed, at position "
					+ entity.Position + ".");
			break;
		case EntityType.Blip:
			AltAsync.Log("A blip has been removed, at position "
					+ entity.Position + ".");
			break;
		case EntityType.Checkpoint:
			AltAsync.Log("A checkpoint has been removed, at position "
					+ entity.Position + ".");
			break;
		default:
			AltAsync.Log("A entity has been removed, at position "
					+ entity.Position + ".");
			break;
	}

	return Task.CompletedTask;
}
```



## OnPlayerConnect

```csharp
{
	AltAsync.Log(player.Name + "has joined the server. (" + reason + ")");

	return Task.CompletedTask;
}
```



## OnPlayerDamage

```csharp
private Task OnPlayerDamage(IPlayer player, IEntity attacker, uint weapon,
    byte damage)
{
	switch (attacker.Type)
	{
		case EntityType.Player:
			var playerAttacker = (IPlayer)attacker;
			AltAsync.Log(player.Name + " has been damaged by " + playerAttacker.Name
					+ " with weapon " + weapon + " and suffered " + damage +
					" HP.");
			break;
		case EntityType.Vehicle:
			var vehicleAttacker = (IVehicle)attacker;
			AltAsync.Log(player.Name + " has been damaged by a vehicle (Driver: "
								+ vehicleAttacker.Driver + ") and suffered "
								+ damage + " HP.");
			break;
		default:
			AltAsync.Log(player.Name + " has been damaged by an Entity and suffered "
								+ damage + ".");
			break;
	}

	return Task.CompletedTask;
}
```



## OnPlayerDead

```csharp
private Task OnPlayerDead(IPlayer player, IEntity killer, uint weapon)
{
	switch (killer.Type)
	{
		case EntityType.Player:
			var playerKiller = (IPlayer)killer;
			AltAsync.Log(player.Name + " has been killed by " + playerKiller.Name
								+ " with weapon " + weapon + ".");
			break;
		case EntityType.Vehicle:
			var vehicleAttacker = (IVehicle)killer;
			AltAsync.Log(player.Name + " has been killed by a vehicle (Driver: "
								+ vehicleAttacker.Driver.Name + ").");
			break;
		default:
			AltAsync.Log(player.Name + " has been killed by an Entity.");
			break;
	}

	return Task.CompletedTask;
}
```



## OnPlayerDisconnect

```csharp
private Task OnPlayerDisconnect(IPlayer player, string reason)
{
	AltAsync.Log(player.Name + "has left the server. (" + reason + ")");

	return Task.CompletedTask;
}
```



## OnVehicleChangeSeat

```csharp
private Task OnVehicleChangeSeat(IVehicle vehicle, IPlayer player, sbyte oldSeat,
	sbyte newSeat)
{
	AltAsync.Log(player.Name + " has changed seat in vehicle (Driver: "
						+ vehicle.Driver.Name + ") from " + oldSeat
						+ " to " + newSeat + ".");

	return Task.CompletedTask;
}
```



## OnVehicleEnter

```csharp
private Task OnVehicleEnter(IVehicle vehicle, IPlayer player, sbyte seat)
{
	AltAsync.Log(player.Name + " entered vehicle (Driver: " + vehicle.Driver.Name
						+ ") on seat " + seat + ".");

	return Task.CompletedTask;
}
```



## OnVehicleLeave

```csharp
private Task OnVehicleLeave(IVehicle vehicle, IPlayer player, sbyte seat)
{
	AltAsync.Log(player.Name + " left vehicle (Driver: " + vehicle.Driver.Name
						+ ") from seat " + seat + ".");

	return Task.CompletedTask;
}
```



## Complete Example

```csharp
using System.Threading.Tasks;
using AltV.Net;
using AltV.Net.Async;
using AltV.Net.Elements.Entities;

namespace CSharp_Examples
{
    public class AsyncEvents : Resource
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
            AltAsync.On("customEvent01", args =>
            {
                AltAsync.Log("customEvent01 triggered with following arguments: " + args[0]);
            });

            // Custom Event Type 02 - Fixed Argument Type
            AltAsync.On<string>("customEvent02", str =>
            {
                AltAsync.Log("customEvent01 triggered with following argument: " + str);
            });

            // Custom Event Type 03 - Delegate Type
            AltAsync.On("customEvent03", delegate (string str)
            {
                AltAsync.Log("customEvent03 triggered with following argument: " + str);
            });

            // Custom Event Type 04 - Method Call
            AltAsync.On<string>("customEvent04", CustomEvent04);

            AltAsync.Log("Resource \"CSharp_Examples\" has been started.");
        }

        private Task OnCheckpoint(ICheckpoint checkpoint, IEntity entity, bool state)
        {
            if (state)
            {
                //Executed if entity enters checkpoint
                switch (entity.Type)
                {
                    case EntityType.Player:
                        AltAsync.Log("A player has entered the checkpoint: player-position "
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
                        break;
                    case EntityType.Vehicle:
                        AltAsync.Log("A vehicle has entered the checkpoint: vehicle-position "
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
                        break;
                    default:
                        AltAsync.Log("A entity has entered the checkpoint: entity-position "
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
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
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
                        break;
                    case EntityType.Vehicle:
                        AltAsync.Log("A vehicle has left the checkpoint: vehicle-position "
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
                        break;
                    default:
                        AltAsync.Log("A entity has left the checkpoint: entity-position "
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
                        break;
                }
            }

            return Task.CompletedTask;
        }

        private Task OnEntityRemove(IEntity entity)
        {
            switch (entity.Type)
            {
                case EntityType.Player:
                    AltAsync.Log("A player has been removed, at position "
                            + entity.Position + ".");
                    break;
                case EntityType.Vehicle:
                    AltAsync.Log("A vehicle has been removed, at position "
                            + entity.Position + ".");
                    break;
                case EntityType.Blip:
                    AltAsync.Log("A blip has been removed, at position "
                            + entity.Position + ".");
                    break;
                case EntityType.Checkpoint:
                    AltAsync.Log("A checkpoint has been removed, at position "
                            + entity.Position + ".");
                    break;
                default:
                    AltAsync.Log("A entity has been removed, at position "
                            + entity.Position + ".");
                    break;
            }

            return Task.CompletedTask;
        }


        private Task OnPlayerConnect(IPlayer player, string reason)
        {
            AltAsync.Log(player.Name + "has joined the server. (" + reason + ")");

            return Task.CompletedTask;
        }

        private Task OnPlayerDamage(IPlayer player, IEntity attacker, uint weapon,
            byte damage)
        {
            switch (attacker.Type)
            {
                case EntityType.Player:
                    var playerAttacker = (IPlayer)attacker;
                    AltAsync.Log(player.Name + " has been damaged by " + playerAttacker.Name
                            + " with weapon " + weapon + " and suffered " + damage +
                            " HP.");
                    break;
                case EntityType.Vehicle:
                    var vehicleAttacker = (IVehicle)attacker;
                    AltAsync.Log(player.Name + " has been damaged by a vehicle (Driver: "
                                        + vehicleAttacker.Driver + ") and suffered "
                                        + damage + " HP.");
                    break;
                default:
                    AltAsync.Log(player.Name + " has been damaged by an Entity and suffered "
                                        + damage + ".");
                    break;
            }

            return Task.CompletedTask;
        }

        private Task OnPlayerDead(IPlayer player, IEntity killer, uint weapon)
        {
            switch (killer.Type)
            {
                case EntityType.Player:
                    var playerKiller = (IPlayer)killer;
                    AltAsync.Log(player.Name + " has been killed by " + playerKiller.Name
                                        + " with weapon " + weapon + ".");
                    break;
                case EntityType.Vehicle:
                    var vehicleAttacker = (IVehicle)killer;
                    AltAsync.Log(player.Name + " has been killed by a vehicle (Driver: "
                                        + vehicleAttacker.Driver.Name + ").");
                    break;
                default:
                    AltAsync.Log(player.Name + " has been killed by an Entity.");
                    break;
            }

            return Task.CompletedTask;
        }

        private Task OnPlayerDisconnect(IPlayer player, string reason)
        {
            AltAsync.Log(player.Name + "has left the server. (" + reason + ")");

            return Task.CompletedTask;
        }

        private Task OnVehicleChangeSeat(IVehicle vehicle, IPlayer player, sbyte oldSeat,
            sbyte newSeat)
        {
            AltAsync.Log(player.Name + " has changed seat in vehicle (Driver: "
                                + vehicle.Driver.Name + ") from " + oldSeat
                                + " to " + newSeat + ".");

            return Task.CompletedTask;
        }

        private Task OnVehicleEnter(IVehicle vehicle, IPlayer player, sbyte seat)
        {
            AltAsync.Log(player.Name + " entered vehicle (Driver: " + vehicle.Driver.Name
                                + ") on seat " + seat + ".");

            return Task.CompletedTask;
        }

        private Task OnVehicleLeave(IVehicle vehicle, IPlayer player, sbyte seat)
        {
            AltAsync.Log(player.Name + " left vehicle (Driver: " + vehicle.Driver.Name
                                + ") from seat " + seat + ".");

            return Task.CompletedTask;
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
        private Task OnPlayerEvent(IPlayer player, string eventName, object[] args)
        {
            switch (eventName)
            {
                case "playerEventA":
                {
                    AltAsync.Log(player.Name + " has triggered Event A, "
                                        + "with following Args:");
                    foreach (var arg in args)
                    {
                        AltAsync.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
                case "playerEventB":
                {
                    AltAsync.Log(player.Name + " has triggered Event B, "
                                        + "with following Args:");
                    foreach (var arg in args)
                    {
                        AltAsync.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
            }

            return Task.CompletedTask;
        }
    }
}

```
