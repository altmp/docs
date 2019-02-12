# Event Examples



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
                Alt.Server.LogDebug("A player has entered the checkpoint: player-position "
                    + entity.Position + " - checkpoint-position " + checkpoint.Position);
                break;
            case EntityType.Vehicle:
                Alt.Server.LogDebug("A vehicle has entered the checkpoint: vehicle-position "
                    + entity.Position + " - checkpoint-position " + checkpoint.Position);
                break;
            default:
                Alt.Server.LogDebug("A entity has entered the checkpoint: entity-position "
                    + entity.Position + " - checkpoint-position " + checkpoint.Position);
                break;
        }
    }
    else
    {
        //Executed if entity leaves checkpoint
        switch (entity.Type)
        {
            case EntityType.Player:
                Alt.Server.LogDebug("A player has left the checkpoint: player-position " + entity.Position + " - checkpoint-position " + checkpoint.Position);
                break;
            case EntityType.Vehicle:
                Alt.Server.LogDebug("A vehicle has left the checkpoint: vehicle-position " + entity.Position + " - checkpoint-position " + checkpoint.Position);
                break;
            default:
                Alt.Server.LogDebug("A entity has left the checkpoint: entity-position " + entity.Position + " - checkpoint-position " + checkpoint.Position);
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
                case EntityType.Player:
                    Alt.Server.LogDebug("A player has been removed, at position " + entity.Position + ".");
                    break;
                case EntityType.Vehicle:
                    Alt.Server.LogDebug("A vehicle has been removed, at position " + entity.Position + ".");
                    break;
                case EntityType.Blip:
                    Alt.Server.LogDebug("A blip has been removed, at position " + entity.Position + ".");
                    break;
                case EntityType.Checkpoint:
                    Alt.Server.LogDebug("A checkpoint has been removed, at position " + entity.Position + ".");
                    break;
                default:
                    Alt.Server.LogDebug("A entity has been removed, at position " + entity.Position + ".");
                    break;
            }
        }
```



## OnPlayerConnect

```csharp
private void OnPlayerConnect(IPlayer player, string reason)
        {
            Alt.Server.LogInfo(player.Name + "has joined the server. (" + reason + ")");
        }
```



## OnPlayerDamage

```csharp
private void OnPlayerDamage(IPlayer player, IEntity attacker, uint weapon, byte damage)
        {
            switch (attacker.Type)
            {
                case EntityType.Player:
                    var playerAttacker = (IPlayer) attacker;
                    Alt.Server.LogDebug(player.Name + " has been damaged by " + playerAttacker + " with weapon " + weapon + " and suffered " + damage + " HP.");
                    break;
                case EntityType.Vehicle:
                    var vehicleAttacker = (IVehicle)attacker;
                    Alt.Server.LogDebug(player.Name + " has been damaged by a vehicle (Driver: " + vehicleAttacker.Driver + ") and suffered " + damage + " HP.");
                    break;
                default:
                    Alt.Server.LogDebug(player.Name + " has been damaged by an Entity and suffered " + damage + ".");
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
                case EntityType.Player:
                    var playerKiller = (IPlayer)killer;
                    Alt.Server.LogDebug(player.Name + " has been killed by " + playerKiller + " with weapon " + weapon + ".");
                    break;
                case EntityType.Vehicle:
                    var vehicleAttacker = (IVehicle)killer;
                    Alt.Server.LogDebug(player.Name + " has been killed by a vehicle (Driver: " + vehicleAttacker.Driver + ").");
                    break;
                default:
                    Alt.Server.LogDebug(player.Name + " has been killed by an Entity.");
                    break;
            }
        }
```



## OnPlayerDisconnect

```csharp
private void OnPlayerDisconnect(IPlayer player, string reason)
        {
            Alt.Server.LogInfo(player.Name + "has left the server. (" + reason + ")");
        }
```



## OnVehicleChangeSeat

```csharp
private void OnVehicleChangeSeat(IVehicle vehicle, IPlayer player, sbyte oldSeat, sbyte newSeat)
        {
            Alt.Server.LogDebug(player.Name + " has changed seat in vehicle (Driver: " + vehicle.Driver.Name + ") from " + oldSeat + " to " + newSeat + ".");
        }
```



## OnVehicleEnter

```csharp
private void OnVehicleEnter(IVehicle vehicle, IPlayer player, sbyte seat)
        {
            Alt.Server.LogDebug(player.Name + " entered vehicle (Driver: " + vehicle.Driver.Name + ") on seat " + seat +  ".");
        }
```



## OnVehicleExit

```csharp
private void OnVehicleLeave(IVehicle vehicle, IPlayer player, sbyte seat)
        {
            Alt.Server.LogDebug(player.Name + " left vehicle (Driver: " + vehicle.Driver.Name + ") from seat " + seat + ".");
        }
```



## Complete Example

```csharp
using AltV.Net;
using AltV.Net.Elements.Entities;
using AltV.Net.Elements.Factories;

namespace CSharp_Examples
{
    public class Events : IResource
    {
        public void OnStart()
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

            // Custom Event Triggers can be found at the bottom
            // Custom Event Type 01
            Alt.On("customEvent01", args =>
            {
                Alt.Server.LogDebug("customEvent01 triggered with following arguments: " + args[0]);
            });

            // Custom Event Type 02 - Fixed Argument Type
            Alt.On<string>("customEvent02", str =>
            {
                Alt.Server.LogDebug("customEvent01 triggered with following argument: " + str);
            });

            // Custom Event Type 03 - Delegate Type
            Alt.On("customEvent03", delegate(string str)
            {
                Alt.Server.LogDebug("customEvent03 triggered with following argument: " + str);
            });

            // Custom Event Type 04 - Method Call
            Alt.On<string>("customEvent04", CustomEvent04);

            Alt.Server.LogInfo("Resource \"CSharp_Examples\" has been started.");
        }

        public void OnStop()
        {
            Alt.Server.LogInfo("Resource \"CSharp_Examples\" has been stopped.");
        }

        public IEntityFactory<IPlayer> GetPlayerFactory()
        {
            return new PlayerFactory();
        }

        public IEntityFactory<IVehicle> GetVehicleFactory()
        {
            return new VehicleFactory();
        }

        public IEntityFactory<IBlip> GetBlipFactory()
        {
            return new BlipFactory();
        }

        public IEntityFactory<ICheckpoint> GetCheckpointFactory()
        {
            return new CheckpointFactory();
        }

        private void OnCheckpoint(ICheckpoint checkpoint, IEntity entity, bool state)
        {
            if (state)
            {
                //Executed if entity enters checkpoint
                switch (entity.Type)
                {
                    case EntityType.Player:
                        Alt.Server.LogDebug("A player has entered the checkpoint: player-position " + entity.Position + " - checkpoint-position " + checkpoint.Position);
                        break;
                    case EntityType.Vehicle:
                        Alt.Server.LogDebug("A vehicle has entered the checkpoint: vehicle-position " + entity.Position + " - checkpoint-position " + checkpoint.Position);
                        break;
                    default:
                        Alt.Server.LogDebug("A entity has entered the checkpoint: entity-position " + entity.Position + " - checkpoint-position " + checkpoint.Position);
                        break;
                }
            }
            else
            {
                //Executed if entity leaves checkpoint
                switch (entity.Type)
                {
                    case EntityType.Player:
                        Alt.Server.LogDebug("A player has left the checkpoint: player-position " + entity.Position + " - checkpoint-position " + checkpoint.Position);
                        break;
                    case EntityType.Vehicle:
                        Alt.Server.LogDebug("A vehicle has left the checkpoint: vehicle-position " + entity.Position + " - checkpoint-position " + checkpoint.Position);
                        break;
                    default:
                        Alt.Server.LogDebug("A entity has left the checkpoint: entity-position " + entity.Position + " - checkpoint-position " + checkpoint.Position);
                        break;
                }
            }
        }

        private void OnEntityRemove(IEntity entity)
        {
            switch (entity.Type)
            {
                case EntityType.Player:
                    Alt.Server.LogDebug("A player has been removed, at position " + entity.Position + ".");
                    break;
                case EntityType.Vehicle:
                    Alt.Server.LogDebug("A vehicle has been removed, at position " + entity.Position + ".");
                    break;
                case EntityType.Blip:
                    Alt.Server.LogDebug("A blip has been removed, at position " + entity.Position + ".");
                    break;
                case EntityType.Checkpoint:
                    Alt.Server.LogDebug("A checkpoint has been removed, at position " + entity.Position + ".");
                    break;
                default:
                    Alt.Server.LogDebug("A entity has been removed, at position " + entity.Position + ".");
                    break;
            }
        }


        private void OnPlayerConnect(IPlayer player, string reason)
        {
            Alt.Server.LogInfo(player.Name + "has joined the server. (" + reason + ")");
        }

        private void OnPlayerDamage(IPlayer player, IEntity attacker, uint weapon, byte damage)
        {
            switch (attacker.Type)
            {
                case EntityType.Player:
                    var playerAttacker = (IPlayer) attacker;
                    Alt.Server.LogDebug(player.Name + " has been damaged by " + playerAttacker + " with weapon " + weapon + " and suffered " + damage + " HP.");
                    break;
                case EntityType.Vehicle:
                    var vehicleAttacker = (IVehicle)attacker;
                    Alt.Server.LogDebug(player.Name + " has been damaged by a vehicle (Driver: " + vehicleAttacker.Driver + ") and suffered " + damage + " HP.");
                    break;
                default:
                    Alt.Server.LogDebug(player.Name + " has been damaged by an Entity and suffered " + damage + ".");
                    break;
            }
        }

        private void OnPlayerDead(IPlayer player, IEntity killer, uint weapon)
        {
            switch (killer.Type)
            {
                case EntityType.Player:
                    var playerKiller = (IPlayer)killer;
                    Alt.Server.LogDebug(player.Name + " has been killed by " + playerKiller + " with weapon " + weapon + ".");
                    break;
                case EntityType.Vehicle:
                    var vehicleAttacker = (IVehicle)killer;
                    Alt.Server.LogDebug(player.Name + " has been killed by a vehicle (Driver: " + vehicleAttacker.Driver + ").");
                    break;
                default:
                    Alt.Server.LogDebug(player.Name + " has been killed by an Entity.");
                    break;
            }
        }

        private void OnPlayerDisconnect(IPlayer player, string reason)
        {
            Alt.Server.LogInfo(player.Name + "has left the server. (" + reason + ")");
        }

        private void OnVehicleChangeSeat(IVehicle vehicle, IPlayer player, sbyte oldSeat, sbyte newSeat)
        {
            Alt.Server.LogDebug(player.Name + " has changed seat in vehicle (Driver: " + vehicle.Driver.Name + ") from " + oldSeat + " to " + newSeat + ".");
        }
        
        private void OnVehicleEnter(IVehicle vehicle, IPlayer player, sbyte seat)
        {
            Alt.Server.LogDebug(player.Name + " entered vehicle (Driver: " + vehicle.Driver.Name + ") on seat " + seat +  ".");
        }

        private void OnVehicleLeave(IVehicle vehicle, IPlayer player, sbyte seat)
        {
            Alt.Server.LogDebug(player.Name + " left vehicle (Driver: " + vehicle.Driver.Name + ") from seat " + seat + ".");
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
            Alt.Server.LogDebug("customEvent04 triggered with following argument: " + str);
        }
    }
}
```

