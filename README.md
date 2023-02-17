# B4X-SocialShare-Library

This is a library to share text in all social apps and not only... You can create from the code a b4xlib and make it a lot easier to use it by creating a >>zip<< file adding in there the manifest.txt as well as the SocialShare.bas file and change the extension to b4xlib. Usage in B4X Pages:

B4X:

<pre>
Sub Class_Globals
    Private Root As B4XView
    Private xui As XUI
    Private sc As SocialShare
  
End Sub

Public Sub Initialize
  
End Sub

'This event will be called once, before the page becomes visible.
Private Sub B4XPage_Created (Root1 As B4XView)
    Root = Root1
    Root.LoadLayout("MainPage")
    sc.Initialize(B4XPages.GetNativeParent(Me), Root)
  
End Sub


Sub Button1_Click

    'For b4i only ChooseChannel is exposed just to make it clearer but if you put also empty string it will work
    sc.ShareMessage("Trial message with url: https://www.google.com", sc.ChooseChannel)
 
#If B4A
    'For B4A you select social channel
    'For example
    sc.ShareMessage("This is a trial message with a URL for Viber  https://www.google.com", sc.Viber)
    'OR
    sc.ShareMessage("This is a trial message with a URL for Twitter   https://www.google.com", sc.Twitter)
#End if
End sub
</pre>
