Since PowerShell 7 no longer has a built in HTML-parser, I want to implement this method, so that it will run in versions > 5.1

```PowerShell
#First... $Result = invoke-webrequest yadayada

function ParseHtml($String) {
    $Unicode = [System.Text.Encoding]::Unicode.GetBytes($String)
    $Html = New-Object -Com 'HTMLFile'
    if ($Html.PSObject.Methods.Name -Contains 'IHTMLDocument2_Write') {
        $Html.IHTMLDocument2_Write($Unicode)
    } 
    else {
        $Html.write($Unicode)
    }
    $Html.Close()
    $Html
}

#Then...
$Document = ParseHtml $Result.Content

#And we should be up to speed..
$Document.getElementsByTagName('table')
```

This will work in PowerShell 7+, but only on Windows.
