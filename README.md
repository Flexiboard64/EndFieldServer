this repository contains a near plug and play server for Arknights Endfield, the server was not made by me,
i just put it toghtere so you can have a much more easier setup, here's what you need to do:

1.Download MongoDB(you don't need MongoDB compass)
2.download fiddler classic
3.install them both 
4.download this repository extract it and put it in a folder
5.go to fiddler to Rules and to CustomizeRules then paste this code there:

  import System;
  import System.Windows.Forms;
  import Fiddler;
  import System.Text.RegularExpressions;
  
  class Handlers
  {
  	static function OnBeforeRequest(oS: Session) {
  		if(
  			oS.fullUrl.Contains("discord") ||
  			oS.fullUrl.Contains("steam") ||
  			oS.fullUrl.Contains("git") ||
  			oS.fullUrl.Contains("yandex")
  			//you can add any addresses if some sites don't work
  		) {
  			oS.Ignore();
  		}
      
  		if (!oS.oRequest.headers.HTTPMethod.Equals("CONNECT")) {
  			if(oS.fullUrl.Contains("gryphline.com") || oS.fullUrl.Contains("hg-cdn.com")) {
  				oS.fullUrl = oS.fullUrl.Replace("https://", "http://");
  				oS.host = "localhost"; // place another ip if you need
  				oS.port = 5000; //and port
  			}
  		}
  	}
  };
6.save it and make sure mongoDB is running and fiddler has CaptureTraffic turned on
7.run the ArkFieldSP.exe and you shold see a command line window saying it's running
8.create an account by typing "account create example" replace example with any username you want
9.launch client and type in the login screen example@anydomain.com, remeber to replace "example" with your username and type any password you want, the password dosen't metter it can be anything example of password: 13g2379gg23gvvrgesgsfg
10. you are ready to play just press on login and start playing! download client from this url because this is the best launcher i have ever tried: https://github.com/CloudTronUSA/Endfield-Launcher


ArkFieldPS server from Hyhyx and SuikoAtari
