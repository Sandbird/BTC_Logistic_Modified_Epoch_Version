Permission granted to redistribute modified version from original author. =BTC= Giallustio

http://www.armaholic.com/page.php?id=12356

Please file bug reports here or @ github repo

http://www.youtube.com/watch?feature=player_detailpage&v=Nb7oM6lYNyU#t=117

<h5>Features / Changes</h5>
=============

U can't lift vehicles with players

U can't lift vehicles that are locked

Different heli's can lift different vehicle classes (easy for admins to change)

Vehicles dropped over 50 altitude deploy a chute

Vehicles drop + will take damage from a fall

U can drop vehicles onto buildings

Custom =BTC= Lift Radar won't show vehicles without line of sight to heli

U cant pickup vehicles without line of sight i.e inside a building

U cant drop vehicles inside a building without line of sight from heli -> vehicle

<h5>Notes</h5>
=============

Works with infiSTAR anti-hack.

Actions to whitelist

[CODE]BTC_SganciaActionId,BTC_liftActionId,BTC_liftHudId,BTC_liftActionId[CODE]

CMDMenus to whitelist

[CODE]'BTC_Hud'[/CODE]

Untested with epoch anti-hack / battleye filters.


<h5>Install Instructions</h5>
=============

Copy mpmission/=BTC=_Logistics to your mission file

Edit your mpmission/init.sqf
Add to the end of the file

// Lift
_logistic = execVM "=BTC=_Logistic\=BTC=_Logistic_Init.sqf";

Edit your mpmission/description.ext
After 
diagHit=1;

Add the contents of mpmission/description-addition.txt

