local old; old = hookmetamethod(game, '__namecall', function(self, ...)
    local args = {...}
    local method = getnamecallmethod()
    
    if not checkcaller() and method == 'FireServer' and self.Name == "Replica_ReplicaSignal" then
--------
        if args[2] == "DamageMine" then
            -- Fast Mining
            for i = 1,9 do
                old(self,...)
            end
        elseif args[2] == "Click" then
            for i = 1,249 do -- Multipler 250 Power/Click
                old(self,...)
            end
        end
--------
    end
    
    return old(self, unpack(args))
end)
