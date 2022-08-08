# copy looks trashy in the file, go to raw for better expirience
# epik guide for C#
//using System.Net ig???
using System.Net;

//getting the path of app...
private string AppPath = Path.GetDirectoryName(Application.ExecutablePath);

//updater
private void Updatedll(string dllName)
{
    WebClient webClient = new WebClient();
    if (dllName == "wrd")
    { 
        string str = webClient.DownloadString(string.Concat("https://raw.githubusercontent.com/GrblxHOfficial/GRH-Executor-Info/main/", dllName));
        string str1 = webClient.DownloadString(str);
        str1.Replace("false ", "");
        str1.Replace("true ", "");
        webClient.DownloadFile(str1, Path.Combine(this.AppPath, string.Concat(dllName, ".dll")));
        // wrd made the process of downloading harder.
    }
    else
    {
        string str2 = webClient.DownloadString(string.Concat("https://raw.githubusercontent.com/GrblxHOfficial/GRH-Executor-Info/main/", dllName));
        webClient.DownloadFile(str2, Path.Combine(this.AppPath, string.Concat(dllName, ".dll")));
        // simple download.
     }
}
