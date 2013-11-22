Permission granted to redistribute modified version from original author. =BTC= Giallustio

http://www.armaholic.com/page.php?id=12356

Please file bug reports here or @ github repo

http://www.youtube.com/watch?feature=player_detailpage&v=Nb7oM6lYNyU#t=117

Features / Changes

U can't lift vehicles with players

U can't lift vehicles that are locked

Different heli's can lift different vehicle classes (easy for admins to change)

Vehicles dropped over 50 altitude deploy a chute

Vehicles drop + will take damage from a fall

U can drop vehicles onto buildings

Custom =BTC= Lift Radar won't show vehicles without line of sight to heli

U cant pickup vehicles without line of sight i.e inside a building

U cant drop vehicles inside a building without line of sight from heli -> vehicle

Notes:-

Works with infiSTAR anti-hack.

Actions to whitelist

[CODE]BTC_SganciaActionId,BTC_liftActionId,BTC_liftHudId,BTC_liftActionId[CODE]

CMDMenus to whitelist

[CODE]'BTC_Hud'[/CODE]

Untested with epoch anti-hack / battleye filters.


Install Instructions

Copy mpmission/=BTC=_Logistics to your mission file

Edit your mpmission/init.sqf
Add to the end of the file

// Lift
_logistic = execVM "=BTC=_Logistic\=BTC=_Logistic_Init.sqf";

Edit your mpmission/description.ext
After 
diagHit=1;

Add

class RscTitles {
	class BTC_Hud
	{
		idd = 1000;
		movingEnable=0;
		duration=1e+011;
		name = "BTC_Hud_Name";
		onLoad = "uiNamespace setVariable ['HUD', _this select 0];";
		controlsBackground[] = {};
		objects[] = {};
		class controls 
		{
			class Radar
			{
				type = 0;
				idc = 1001;
				style = 48;
				x = (SafeZoneW+2*SafeZoneX) - 0.1;//safezonex + 0.1;//0.9
				y = (SafeZoneH+2*SafeZoneY) - 0.15;//safezoney + 0.1;//0.85
				w = 0.3;
				h = 0.4;
				font = "Zeppelin32";
				sizeEx = 0.03;
				colorBackground[] = {0, 0, 0, 0};
				colorText[] = {1, 1, 1, 1};
				text = "\ca\ui\data\igui_radar_air_ca.paa";
			};
			class Img_Obj
			{
				type = 0;
				idc = 1002;
				style = 48;
				x = (SafeZoneW+2*SafeZoneX) + 0.045;
				y = (SafeZoneH+2*SafeZoneY) + 0.045;
				w = 0.01;
				h = 0.01;
				font = "Zeppelin32";
				sizeEx = 0.04;
				colorBackground[] = {0, 0, 0, 0};
				colorText[] = {1, 1, 1, 1};
				text = "=BTC=_Logistic\data\=BTC=_Obj.paa";
			};
			class Pic_Obj
			{
				type = 0;
				idc = 1003;
				style = 48;
				x = (SafeZoneW+2*SafeZoneX) - 0.125;
				y = (SafeZoneH+2*SafeZoneY) - 0.23;
				w = 0.1;
				h = 0.1;
				font = "Zeppelin32";
				sizeEx = 0.03;
				colorBackground[] = {0, 0, 0, 0};
				colorText[] = {1, 1, 1, 1};
				text = "";
			};
			class Arrow
			{
				type = 0;
				idc = 1004;
				style = 48;
				x = (SafeZoneW+2*SafeZoneX) + 0.15;
				y = (SafeZoneH+2*SafeZoneY) - 0.15;
				w = 0.05;
				h = 0.05;
				font = "Zeppelin32";
				sizeEx = 0.03;
				colorBackground[] = {0, 0, 0, 0};
				colorText[] = {1, 1, 1, 1};
				text = "";
			};
			class Type_Obj
			{
				type = 0;
				idc = 1005;
				style = 0x00;
				x = (SafeZoneW+2*SafeZoneX) - 0.03;
				y = (SafeZoneH+2*SafeZoneY) - 0.335;
				w = 0.3;
				h = 0.3;
				font = "Zeppelin32";
				sizeEx = 0.03;
				colorBackground[] = {0, 0, 0, 0};
				colorText[] = {1, 1, 1, 1};
				text = "";
			};
		};   
	};
	class ExampleTitle {     
		idd = -1; 
		duration = 10; //show for 10 seconds 
		class controls 
		{ 
			class ExampleControl 
			{
				idc = -1; 
				type = 0; 
				style = 2; //centre text 
				x = safeZoneX + safeZoneW - 0.6 * 3 / 4;  
				y = safeZoneY + safeZoneH - 0.6; 
				h = 0.6; 
				w = 0.6 * 3 / 4; //w == h 
				font = "EtelkaNarrowMediumPro"; 
				sizeEx = 0.03; 
				colorBackground[] = {1,1,0,1}; //yellow background 
				colorText[] = {0,0,1,1}; //blue text 
				text = "Bottom Right Corner Square Box"; 
			};
		};
	};
};
