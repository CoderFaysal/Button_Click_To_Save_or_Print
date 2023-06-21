# Button Click To Save or Print

## Result Download Button


#### public class
```
FloatingActionButton fab;
```

#### onCreate

```
fab = findViewById(R.id.fab);
fab.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        // Code Here ==========
       createWebPrintJob(webView);
   }
});

```

#### Create a Function

```
private void createWebPrintJob(WebView webView) {
        PrintManager printManager = (PrintManager) this.getSystemService(Context.PRINT_SERVICE);
        PrintDocumentAdapter printAdapter = webView.createPrintDocumentAdapter();
        String jobName = getString(R.string.app_name) + " Print Result";
        printManager.print(jobName, printAdapter, new PrintAttributes.Builder().build());
    }
```
