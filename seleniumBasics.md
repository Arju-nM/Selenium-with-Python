# Selenium Basics

## Opening a browser  
```python
driver = webdriver.Chrome()
```

## Opening a url 
```python
driver.get('http://www.google.com')
```
When you try the above command once again for a different (or same) url it is opened on the same tab.

## Opening a new tab
```python
driver.execute_script("window.open('');")
```

## Navigating through tabs
```python
#n - a valid number (limit is the number of tabs open)
driver.switch_to.window(driver.window_handles[n])
```

## Closing a tab
 ```python
 driver.close()
```
Closes the currently active tab, if only one tab is open then the window is closed

## Searching in google
```python
#Opening Google in Chrome
driver = webdriver.Chrome()
driver.get('http://www.google.com')

#Select the search bar
searchBar = driver.find_element_by_name('q') # 'q' is the name of the search bar 

# Searching with key
searchBar.send_keys('search key') # Enter search key of choice
searchBar.send_keys(Keys.RETURN) # Hit return after you enter search text
```

## Searching in some other url
```python
#Get to the url in Chrome
driver = webdriver.Chrome()
driver.get(url) # Enter url of choice

#Select the search bar
searchBar = driver.find_element_by_name(searchBarName) #  Get and enter the search bar name

# Searching with key
searchBar.send_keys('search key') # Enter search key of choice
searchBar.send_keys(Keys.RETURN) # Hit return after you enter search text
```

## Finding the search bar name
Steps:
1. Go to the desired url
2. Right click on the search bar and click **Inspect Element**
3. Find the value of name in the highlighted 

Example:

Go to amazon.com<br/> 
<br/>![](/Images/picture1.png)<br/>

<br/><br/>Right click in the search bar and select Inspect Element (or `Ctrl+Shift+I`)<br/>
<br/>![](/Images/picture2.png)<br/>  

<br/><br/>Search for name in highlighted text<br/>
<br/>![](/Images/picture3.png)<br/>  

<br/><br/>This is the searchBarName that has to be entered in `find_element_by_name(searchBarName)`<br/>
<br/>![](/Images/picture4.png)<br/>
