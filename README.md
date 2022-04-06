
# Rapport

**Assignment 2: Views & WebView**

En webview som syns i kod nedan gör det möjligt att visa en HTML hemsida. Vi har bestämt en höjd och bredd som gör att
den fyller hela skärmen och sen en margin på 55dp som gör att allt innehåll endast visas under nav baren, som är 55dp.


```
    <WebView
        android:id="@+id/my_webview"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_marginTop="55dp" />
```

Sedan i huvudfilen för java koden bestämmer man att en variabel som skapats (myWebView) ska visas i den view som har id
"my_webview" som skapades i XML filen. Sedan behöver man också aktivera JavaScript som görs i rad två i kod nedan.

```
        myWebView = findViewById(R.id.my_webview);
        myWebView.getSettings().setJavaScriptEnabled(true);
```

När användaren klickar på navigationsmenyn som finns i toppen triggas _"onOptionsItemSelected"_ som sedan har två _if_
satser som körs beroende på vilken meny som valts. Och denna kallar sedan på koden som syns nedan, som är två olika
klasser som bestämmer URL:en för myWebView variabeln. Nedan syns också bild för intern och extern webbsida

```
    public void showExternalWebPage(){
        myWebView.loadUrl("https://www.formula1.com");
    }

    public void showInternalWebPage(){
        myWebView.loadUrl("file:///android_asset/index.html");
    }
```

![](external.png | width=30)
![](internal.png | width=30)