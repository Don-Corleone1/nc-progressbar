![image](https://user-images.githubusercontent.com/123836372/215287946-35d49410-b0e4-4058-b1a9-5a6a38760598.png)
Download the script then drag it to -  [standalone] folder.
Add the following code to your server.cfg/resouces.cfg

function QBCore.Functions.Progressbar(name, label, duration, useWhileDead, canCancel, disableControls, animation, prop, propTwo, onFinish, onCancel)
    exports['nc-progressbar']:Progress({
        name = name:lower(),
        duration = duration,
        label = label,
        useWhileDead = useWhileDead,
        canCancel = canCancel,
        controlDisables = disableControls,
        animation = animation,
        prop = prop,
        propTwo = propTwo,
    }, function(cancelled)
        if not cancelled then
            if onFinish then
                onFinish()
            end
        else
            if onCancel then
                onCancel()
            end
        end
    end)
end
