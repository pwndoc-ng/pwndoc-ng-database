# Pwndoc-NG Database

This repository contain vulnerabilities databases for pwndoc-ng and custom templates.




# Vulnerabilities

https://user-images.githubusercontent.com/53094530/217284618-c0b2ad71-465c-40af-87db-1111c33f8490.mp4


If you want to pre-populate your pwndoc-ng with vulnerabilities:

1. The vulnerabilities are taken from the spreadsheet from https://github.com/JulianGR/OWASP_WSTG_ASVS
2. To import them, 
    1. Create 'es' and 'en' locales. They have to be exactly that, otherwise pwndoc-ng won't recognize the vulns.
    2. Use the two `.json` files and go to Custom data > Import
3. To merge them automatically, just like in the video, donwload the Selenium extension in your browser. NOTE: for me, it worked only in Firefox (https://addons.mozilla.org/es/firefox/addon/selenium-ide/), NOT in Chrome or Opera.
4. Open the script and click "Run all test"
5. Success 




# For developers

## Parsing script
If you are an user and want to import vulns, you don't have to use the script. However, if you want more control over what you import, there are a few considerations:

+ If you want a different locale, change the main:

```py
# main([NAME OF THE SPREADSHEET FILE], [NAME OF THE SHEET], [LOCALE], [CATEGORY OF VULNS])
```

+ The script is very much customized to parse the spreadsheet. For example, the spreadsheet is converted to markdown so that when vulns appear with format in pwndoc-ng. If there are future changes to the spreadsheet, I will make the script compatible. More languages are going to be added with time (pull request them =D )
+ If you want to add custom fields to vulnerabilities, you have to first export in `.yaml` vulnerabilites that you created by hand with the parameter, then figure out which ID they have, then paste and uncomment the "custom field section" in the script


## Selenium script
+ Right now, the loop is executed 118 times since there are exactly 118 vulnerabilities in the spreadsheet. Again, if there are future changes to the spreadsheet, I will make the script compatible. More languages are going to be added with time (pull request them =D )



