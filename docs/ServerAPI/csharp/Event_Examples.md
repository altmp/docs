## Event Examples



## OnCheckpoint

```csharp
private void OnCheckpoint(ICheckpoint checkpoint, IEntity entity, bool state)
{
	if (state)
	{
		//Executed if entity enters checkpoint
		switch (entity.Type)
		{
			case EntityType.Player:
				Alt.Log("A player has entered the checkpoint: player-position "
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
				break;
			case EntityType.Vehicle:
				Alt.Log("A vehicle has entered the checkpoint: vehicle-position "
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
				break;
			default:
				Alt.Log("A entity has entered the checkpoint: entity-position "
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
			case BaseObjectType.Player:
				Alt.Log("A player has left the checkpoint: player-position "
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
				break;
			case BaseObjectType.Vehicle:
				Alt.Log("A vehicle has left the checkpoint: vehicle-position "
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
				break;
			default:
				Alt.Log("A entity has left the checkpoint: entity-position "
						+ entity.Position + " - checkpoint-position "
						+ checkpoint.Position);
				break;
		}
	}
}
```



## OnEntityRemove

```csharp
private void OnEntityRemove(IEntity entity)
{
	switch (entity.Type)
	{
		case BaseObjectType.Player:
			Alt.Log("A player has been removed, at position " 
					+ entity.Position + ".");
			break;
		case BaseObjectType.Vehicle:
			Alt.Log("A vehicle has been removed, at position "
					+ entity.Position + ".");
			break;
		case BaseObjectType.Blip:
			Alt.Log("A blip has been removed, at position "
					+ entity.Position + ".");
			break;
		case BaseObjectType.Checkpoint:
			Alt.Log("A checkpoint has been removed, at position "
					+ entity.Position + ".");
			break;
		default:
			Alt.Log("A entity has been removed, at position "
					+ entity.Position + ".");
			break;
	}
}
```



## OnPlayerConnect

```csharp
private void OnPlayerConnect(IPlayer player, string reason)
{
	Alt.Log(player.Name + "has joined the server. (" + reason + ")");
}
```



## OnPlayerDamage

```csharp
private void OnPlayerDamage(IPlayer player, IEntity attacker, uint weapon, byte damage)
{
	switch (attacker.Type)
	{
		case BaseObjectType.Player:
			var playerAttacker = (IPlayer) attacker;
			Alt.Log(player.Name + " has been damaged by " + playerAttacker.Name 
					+ " with weapon " + weapon + " and suffered " + damage + " HP.");
			break;
		case BaseObjectType.Vehicle:
			var vehicleAttacker = (IVehicle)attacker;
			Alt.Log(player.Name + " has been damaged by a vehicle (Driver: " 
								+ vehicleAttacker.Driver + ") and suffered " 
								+ damage + " HP.");
			break;
		default:
			Alt.Log(player.Name + " has been damaged by an Entity and suffered " 
								+ damage + ".");
			break;
	}
}
```



## OnPlayerDead

```csharp
private void OnPlayerDead(IPlayer player, IEntity killer, uint weapon)
{
	switch (killer.Type)
	{
		case BaseObjectType.Player:
			var playerKiller = (IPlayer)killer;
			Alt.Log(player.Name + " has been killed by " + playerKiller.Name
								+ " with weapon " + weapon + ".");
			break;
		case BaseObjectType.Vehicle:
			var vehicleAttacker = (IVehicle)killer;
			Alt.Log(player.Name + " has been killed by a vehicle (Driver: " 
								+ vehicleAttacker.Driver.Name + ").");
			break;
		default:
			Alt.Log(player.Name + " has been killed by an Entity.");
			break;
	}
}
```



## OnPlayerDisconnect

```csharp
private void OnPlayerDisconnect(IPlayer player, string reason)
{
	Alt.Log(player.Name + "has left the server. (" + reason + ")");
}
```



## OnVehicleChangeSeat

```csharp
private void OnVehicleChangeSeat(IVehicle vehicle, IPlayer player, sbyte oldSeat,
	sbyte newSeat)
{
	Alt.Log(player.Name + " has changed seat in vehicle (Driver: " 
						+ vehicle.Driver.Name + ") from " + oldSeat 
						+ " to " + newSeat + ".");
}
```



## OnVehicleEnter

```csharp
private void OnVehicleEnter(IVehicle vehicle, IPlayer player, sbyte seat)
{
	Alt.Log(player.Name + " entered vehicle (Driver: " + vehicle.Driver.Name 
						+ ") on seat " + seat +  ".");
}
```



## OnVehicleLeave

```csharp
private void OnVehicleLeave(IVehicle vehicle, IPlayer player, sbyte seat)
{
	Alt.Log(player.Name + " left vehicle (Driver: " + vehicle.Driver.Name 
						+ ") from seat " + seat + ".");
}
```



## Complete Example

```csharp
using System.Collections;
using AltV.Net;
using AltV.Net.Elements.Entities;

namespace CSharp_Examples
{
    public class Events : Resource
    {
        public override void OnStart()
        {
            // Event Definitions
            Alt.OnCheckpoint += OnCheckpoint;
            Alt.OnEntityRemove += OnEntityRemove;
            Alt.OnPlayerConnect += OnPlayerConnect;
            Alt.OnPlayerDamage += OnPlayerDamage;
            Alt.OnPlayerDead += OnPlayerDead;
            Alt.OnPlayerDisconnect += OnPlayerDisconnect;
            Alt.OnVehicleChangeSeat += OnVehicleChangeSeat;
            Alt.OnVehicleEnter += OnVehicleEnter;
            Alt.OnVehicleLeave += OnVehicleLeave;

            Alt.OnPlayerCustomEvent += OnPlayerCustomEvent;
            Alt.OnPlayerEvent += OnPlayerEvent;
            Alt.OnServerCustomEvent += OnServerCustomEvent;
            Alt.OnServerEvent += OnServerEvent;

            // Custom Event Triggers can be found at the bottom
            // Custom Event Type 01
            Alt.On("customEvent01", args =>
            {
                Alt.Log("customEvent01 triggered with following arguments: " + args[0]);
            });

            // Custom Event Type 02 - Fixed Argument Type
            Alt.On<string>("customEvent02", str =>
            {
                Alt.Log("customEvent01 triggered with following argument: " + str);
            });

            // Custom Event Type 03 - Delegate Type
            Alt.On("customEvent03", delegate(string str)
            {
                Alt.Log("customEvent03 triggered with following argument: " + str);
            });

            // Custom Event Type 04 - Method Call
            Alt.On<string>("customEvent04", CustomEvent04);

            Alt.Log("Resource \"CSharp_Examples\" has been started.");
        }

        public override void OnStop()
        {
            Alt.Log("Resource \"CSharp_Examples\" has been stopped.");
        }

        private void OnCheckpoint(ICheckpoint checkpoint, IEntity entity, bool state)
        {
            if (state)
            {
                //Executed if entity enters checkpoint
                switch (entity.Type)
                {
                    case BaseObjectType.Player:
                        Alt.Log("A player has entered the checkpoint: player-position "
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
                        break;
                    case BaseObjectType.Vehicle:
                        Alt.Log("A vehicle has entered the checkpoint: vehicle-position "
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
                        break;
                    default:
                        Alt.Log("A entity has entered the checkpoint: entity-position "
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
                    case BaseObjectType.Player:
                        Alt.Log("A player has left the checkpoint: player-position "
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
                        break;
                    case BaseObjectType.Vehicle:
                        Alt.Log("A vehicle has left the checkpoint: vehicle-position "
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
                        break;
                    default:
                        Alt.Log("A entity has left the checkpoint: entity-position "
                                + entity.Position + " - checkpoint-position "
                                + checkpoint.Position);
                        break;
                }
            }
        }

        private void OnEntityRemove(IEntity entity)
        {
            switch (entity.Type)
            {
                case BaseObjectType.Player:
                    Alt.Log("A player has been removed, at position " 
                            + entity.Position + ".");
                    break;
                case BaseObjectType.Vehicle:
                    Alt.Log("A vehicle has been removed, at position "
                            + entity.Position + ".");
                    break;
                case BaseObjectType.Blip:
                    Alt.Log("A blip has been removed, at position "
                            + entity.Position + ".");
                    break;
                case BaseObjectType.Checkpoint:
                    Alt.Log("A checkpoint has been removed, at position "
                            + entity.Position + ".");
                    break;
                default:
                    Alt.Log("A entity has been removed, at position "
                            + entity.Position + ".");
                    break;
            }
        }


        private void OnPlayerConnect(IPlayer player, string reason)
        {
            Alt.Log(player.Name + "has joined the server. (" + reason + ")");
        }

        private void OnPlayerDamage(IPlayer player, IEntity attacker, uint weapon, 
            byte damage)
        {
            switch (attacker.Type)
            {
                case BaseObjectType.Player:
                    var playerAttacker = (IPlayer) attacker;
                    Alt.Log(player.Name + " has been damaged by " + playerAttacker.Name 
                            + " with weapon " + weapon + " and suffered " + damage +
                            " HP.");
                    break;
                case BaseObjectType.Vehicle:
                    var vehicleAttacker = (IVehicle)attacker;
                    Alt.Log(player.Name + " has been damaged by a vehicle (Driver: " 
                                        + vehicleAttacker.Driver + ") and suffered " 
                                        + damage + " HP.");
                    break;
                default:
                    Alt.Log(player.Name + " has been damaged by an Entity and suffered " 
                                        + damage + ".");
                    break;
            }
        }

        private void OnPlayerDead(IPlayer player, IEntity killer, uint weapon)
        {
            switch (killer.Type)
            {
                case BaseObjectType.Player:
                    var playerKiller = (IPlayer)killer;
                    Alt.Log(player.Name + " has been killed by " + playerKiller.Name
                                        + " with weapon " + weapon + ".");
                    break;
                case BaseObjectType.Vehicle:
                    var vehicleAttacker = (IVehicle)killer;
                    Alt.Log(player.Name + " has been killed by a vehicle (Driver: " 
                                        + vehicleAttacker.Driver.Name + ").");
                    break;
                default:
                    Alt.Log(player.Name + " has been killed by an Entity.");
                    break;
            }
        }

        private void OnPlayerDisconnect(IPlayer player, string reason)
        {
            Alt.Log(player.Name + "has left the server. (" + reason + ")");
        }

        private void OnVehicleChangeSeat(IVehicle vehicle, IPlayer player, sbyte oldSeat,
            sbyte newSeat)
        {
            Alt.Log(player.Name + " has changed seat in vehicle (Driver: " 
                                + vehicle.Driver.Name + ") from " + oldSeat 
                                + " to " + newSeat + ".");
        }
        
        private void OnVehicleEnter(IVehicle vehicle, IPlayer player, sbyte seat)
        {
            Alt.Log(player.Name + " entered vehicle (Driver: " + vehicle.Driver.Name 
                                + ") on seat " + seat +  ".");
        }

        private void OnVehicleLeave(IVehicle vehicle, IPlayer player, sbyte seat)
        {
            Alt.Log(player.Name + " left vehicle (Driver: " + vehicle.Driver.Name 
                                + ") from seat " + seat + ".");
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
            Alt.Log("customEvent04 triggered with following argument: " + str);
        }

        //Can been triggered from a Server Event
        private void OnServerEvent(string eventName, object[] args)
        {
            switch (eventName)
            {
                case "eventA":
                {
                    Alt.Log("Server Event A has been triggered, with following Args:");
                    foreach (var arg in args)
                    {
                        Alt.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
                case "eventB":
                {
                    Alt.Log("Server Event B has been triggered, with following Args:");
                    foreach (var arg in args)
                    {
                        Alt.Log(arg + " - Type: " + arg.GetType());
                    }
                        break;
                }
            }
        }

        // Can been triggered from a custom Server Event, if you want to parse the
        // MValueList on your own
        private void OnServerCustomEvent(string eventName, 
            ref AltV.Net.Native.MValueArray mValueArray)
        {
            switch (eventName)
            {
                case "eventCustomA":
                {
                    Alt.Log("Custom Server Event A has been triggered, " +
                            "with following Args:");
                    foreach (var arg in mValueArray.ToArray())
                    {
                        Alt.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
                case "eventCustomB":
                {
                    Alt.Log("Custom Server Event B has been triggered, " + 
                            "with following Args:");
                    foreach (var arg in mValueArray.ToArray())
                    {
                        Alt.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
            }
        }

        // Can been triggered from a Client Event
        private void OnPlayerEvent(IPlayer player, string eventName, object[] args)
        {
            switch (eventName)
            {
                case "playerEventA":
                {
                    Alt.Log(player.Name + " has triggered Event A, "
                                        + "with following Args:");
                    foreach (var arg in args)
                    {
                        Alt.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
                case "playerEventB":
                {
                    Alt.Log(player.Name + " has triggered Event B, "
                                        + "with following Args:");
                    foreach (var arg in args)
                    {
                        Alt.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
            }
        }

        // Can been triggered from a custom Client Event, if you want to parse the
        // MValueList on your own
        private void OnPlayerCustomEvent(IPlayer player, string eventName, 
            ref AltV.Net.Native.MValueArray mValueArray)
        {
            switch (eventName)
            {
                case "playerEventA":
                {
                    Alt.Log(player.Name + " has triggered Custom Event A, "
                                        + "with following Args:");
                    foreach (var arg in mValueArray.ToArray())
                    {
                        Alt.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
                case "playerEventB":
                {
                    Alt.Log(player.Name + " has triggered Custom Event B, "
                                        + "with following Args:");
                    foreach (var arg in mValueArray.ToArray())
                    {
                        Alt.Log(arg + " - Type: " + arg.GetType());
                    }
                    break;
                }
            }
        }

    }
}
```
