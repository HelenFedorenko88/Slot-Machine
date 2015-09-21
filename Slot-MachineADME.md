# Slot-Machine 

It's web based slot machine game made using cocos2d-js.
This game is optimized well for cross platform. It's able to work ios android and web browsers.

## How to use it? 
### SlotMachine class .

This class is based node class of cc engine. So you can use this class using the methods like other node classes on the game scene. (layer based).

        var SlotMachine = cc.Node.extend(
        {
                ...
        }


It's very simple to use. You can add it using a few code lines.

for example you can add it using following code.

        var _slotMachine = new SlotMachine("Frame.png","FrameMask.png"); // create a slot machine. you can create more slot machines.
        var centerPos = cc.p(320, 200); // set position of slot machine.
        _slotMachine.setPosition(centerPos);
        _slotMachine.setScale(0.5); // set scale.
        this.addChild(_slotMachine, 1,1); // add slotmachine object to cc.layer
        _slotMachine,spin(); // spin the reels in slot machine.
        
        
### Public Members 
####  - Constructor .
  You have to use following styles to create Slot Machine object.
  
    SlotMachine (backImage, maskImage, reels, orderOfReels);
    
    // @param 1 : background image. this image will be laid on final layer of Zorder.  ex : "background.png"
    // @param 2 : mask image. this image will be laid on top layer of Zorder. this image is very important,
    //            added images on SlotMachineFrame node can not be rendered at outside of that image's boundary .  ex : "mask.png"
    // @param 3 : array of reels. this value must be following format.  type : [{base_image:"x.png", scale:scale, normal_action:action1, stop_action:action2, win_action:action3}, ... ]
    // @param 4 : orders of index of reels per each row. this value must be following format. ex : [[0,1,3,2,2,1,4,6,3,5,], [...] ,[...]]
    // return : returns a instance of Slotmachine class. 
    
    ex :  var _slotMachine = new SlotMachine("Frame.png","FrameMask.png"); // create a slot machine. you can create more slot machines.

#### -spin()
    Spin the reels in a slot machine. You can ignore parameters. In this case that parameters will be set random value.

    spin:function(leftSpinCount, centerSpinCount, rightSpinCount);
    
    // spin reels.
    // @param1 : spin count of left reels.
    // @param2 : spin count of center reels.
    // @param3 : spin count of right reels.
    // return : if the reels are spinning now, it will be returned false, other case will be returned true.
    
    ex : _slotMachine.spin();
    
#### -bet()
    Bet the amount and paylines.
    
    bet:function (countOfPayLine, amount);
    
    // bet the amount and pay lines.
    // @param1 : count of pay line. 1 ~ MaxPayLines
    // @param2 : betting amount.
    
    ex : bet(3, 200);
    
#### -getCurrentReelState()    
    Get the state of current reels.
    
    getCurrentReelState() ;
    
    // get the state of current reels.
     // return : the state of current reels. format : [[RS00, RS01, RS02], [RS10, RS11, RS12],[RS20, RS21, RS22]]
    
    ex : var aryOfReelsState = getCurrentReelState(); 
    
    
    
    
    
        
        
