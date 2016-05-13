# Untrusted
My Untrusted Solutions -> https://alexnisnevich.github.io/untrusted/

## Level 1
Go over the ⌘

```Leave empty```

## Level 2
Comment the code

```/* ```

```*/ ```

## Level 3
Replace the original code with and go through the hole
```
for (y = 12; y <= map.getHeight() - 3; y++) {
  map.placeObject(5, y, 'block');
  map.placeObject(map.getWidth() - 5, y, 'block');
  }
for (x = 1; x <= map.getWidth() - 5; x++) {
  map.placeObject(x, 10, 'block');
  map.placeObject(x, map.getHeight() - 3, 'block');
}
```

## Level 4
Add a extra exit
```
map.placeObject(map.getWidth() - 5, 10, 'exit');
```

## Level 5
Change the color of the mines so you can avoid them
```
map.setSquareColor(x, y, '#fff');
```

## Level 6
Create a blockade so that the drone is stuck
```
map.placeObject(map.getWidth()-11, 11, 'block');
map.placeObject(map.getWidth()-12, 11, 'block');
map.placeObject(map.getWidth()-12, 12, 'block');
```

## Level 7
Call to change color
```
var player = map.getPlayer();
        
        switch(player.getColor()) {
            case "#0f0":
                player.setColor('#f00');
                break;
            case "#f00":
                player.setColor('#ff0');
                break;
            case "#ff0":
            default:
                player.setColor('#0f0');
                break;
        }
```

## Level 8
Call to change the forest and make your way through it

Replace `movePlayerToExit` for `generateForest`

## Level 9
Stand on the raft, call and move forwards
```
map.getPlayer().setPhoneCallback(function() {
        raftDirection = 'up';
    });
```

## Level 10
Just move and the drones will get out of the way
```
if (me.getY() != 11) {
            if (me.canMove("up")) {
            me.move("up");
            }
            else {
            me.move("left");
            }
            }
```
```
Leave empty
```
```
if (me.getY() != 11) {
            if (me.canMove("up")) {
            me.move("up");
            }
            else {
            me.move("right");
            }
            }
```

## Level 11
Move and the R will come to you. Go over the R when he gets out of the cell
```
if (me.canMove("down")) {
            me.move("down");
            }
            else {
            me.move("right");
            }
```

## Level 12
Move and the R will come to you. Go over the R when he gets out of the cell
```
if (me.getX() < 5) {
                me.move('right');
            }
            else if (me.getX() == 5 && me.getY() < 5) {
                me.move('down');
            }
            else if (me.getX() < 20 && me.getY() == 5) {
            	me.move('right');
  			}
            else if (me.getX() == 20 && me.getY() > 4) {
            	me.move('up');
            }
            else if (me.canMove("right")) {
            	me.move('right');
            }
            else if (me.getY()  < 10) {
          	  	me.move('down');
```

## Level 13
```
if (!me.last_move) me.last_move = 'right';
if (me.last_move == 'right') {
if (me.canMove('up')) {
me.last_move = 'up';
me.move('up');
} else if (me.canMove('right')) {
me.last_move = 'right';
me.move('right');
} else if (me.canMove('down')) {
me.last_move = 'down';
me.move('down');
} else if (me.canMove('left')) {
me.last_move = 'left';
me.move('left');
}
} else if (me.last_move == 'up') {
if (me.canMove('left')) {
me.last_move = 'left';
me.move('left');
} else if (me.canMove('up')) {
me.last_move = 'up';
me.move('up');
} else if (me.canMove('right')) {
me.last_move = 'right';
me.move('right');
} else if (me.canMove('down')) {
me.last_move = 'down';
me.move('down');
}
} else if (me.last_move == 'left') {
if (me.canMove('down')) {
me.last_move = 'down';
me.move('down');
} else if (me.canMove('left')) {
me.last_move = 'left';
me.move('left');
} else if (me.canMove('up')) {
me.last_move = 'up';
me.move('up');
} else if (me.canMove('right')) {
me.last_move = 'right';
me.move('right');
}
} else if (me.last_move == 'down') {
if (me.canMove('right')) {
me.last_move = 'right';
me.move('right');
} else if (me.canMove('down')) {
me.last_move = 'down';
me.move('down');
} else if (me.canMove('left')) {
me.last_move = 'left';
me.move('left');
} else if (me.canMove('up')) {
me.last_move = 'up';
me.move('up');
}
}
```

## Level 14

Change `greenKey` for `theAlgorithm`

Move to the left upper corner

Then to the right upper corner

Then tot the right entrence on the bottom

Then through the blue entrence to the A 

Finaly move to the exit

## Level 15

Replace `'drowning in deep dark water'` with `theAlgorithm` (Without the apostrophe!)

## Level 16
Call to change your color and make your way through the lazers

Replace `ctx.strokeStyle = 'white';` with `ctx.strokeStyle = color;`
``` 
var player = map.getPlayer();
       var colors = ['red', 'yellow', 'teal'];        
    player.index = -1;
    function changeColor() {
        player.index = (player.index + 1)%3;
        player.setColor(colors[player.index]);
    }
    changeColor();
    player.setPhoneCallback(changeColor);
```
## Level 17

Follow the lines. I finished the first time without the code and just being lucky
```
function goto(ctx, method, target) {
            var info = map.getCanvasCoords(target);
            ctx[method](info.x,info.y);
        }
        
        if((t1.getType() == 'teleporter') && (t2.getType() =='teleporter')) {
            var ctx = map.getCanvasContext();
            ctx.beginPath();
            ctx.strokeStyle = 'blue';
            ctx.lineWidth = 2;
            goto(ctx,'moveTo', t1);
            goto(ctx,'lineTo', t2);
            ctx.stroke();            
       }
```
##Level 18
Call to make a bridge
```
map.defineObject('barrier', {
        'symbol': '░',
        'color': 'green',
        'impassable': true,
        'passableFor': ['robot']
      });
      
      for (var x = fl(w/2) - 5; x < fl(w/2) + 5; x++) {
        map.placeObject(x, fl(h/2), 'barrier');
        
      }
```

## Level 19 - 25
Work in progress
