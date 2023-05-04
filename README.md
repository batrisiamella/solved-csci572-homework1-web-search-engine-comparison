Download Link: https://assignmentchef.com/product/solved-csci572-homework1-web-search-engine-comparison
<br>
This exercise is about comparing the search results from Google versus different search engines. Many search engine comparison studies have been done. All of them use samples of data, some small and some large, so no definitive conclusions can be drawn. But it is always instructive to see how two search engines match up, even on a small data set.The process you will follow is to issue a set of queries and to evaluate how closely the results of the two search engines compare. You will compare the results from the search engine that you are assigned to with the results from Google (provided by us on the class website).

<strong>Note</strong>: Please stick with the assigned dataset and search engine according to your ID number. PLEASE don’t work on another dataset and later ask for an exception.




<table width="624">

 <tbody>

  <tr>

   <td width="116"><strong>USC ID ends with </strong></td>

   <td width="169"><strong>Query Data Set </strong></td>

   <td width="169"><strong>Google Reference Dataset </strong></td>

   <td width="169"><strong>Assigned Search Engine </strong></td>

  </tr>

  <tr>

   <td width="116">01~25</td>

   <td width="169">100QueriesSet1</td>

   <td width="169">Google_Result1.json</td>

   <td width="169">Bing</td>

  </tr>

  <tr>

   <td width="116">26~50</td>

   <td width="169">100QueriesSet2</td>

   <td width="169">Google_Result2.json</td>

   <td width="169">Yahoo!</td>

  </tr>

  <tr>

   <td width="116">51~75</td>

   <td width="169">100QueriesSet3</td>

   <td width="169">Google_Result3.json</td>

   <td width="169">Ask</td>

  </tr>

  <tr>

   <td width="116">76~99</td>

   <td width="169">100QueriesSet4</td>

   <td width="169">Google_Result4.json</td>

   <td width="169">Teoma</td>

  </tr>

 </tbody>

</table>




<h1>THE QUERIES</h1>

The queries will be given to you in a text file, one query per line. Each file contains 100 queries. These are actual queries extracted from query log files of several search engines. Here is a sample of some of the queries:




The European Union includes how many countries

What are Mia Hamms accomplishments

Which form of government is still in place in Greece

When was the canal de panama built

What color is the black box on commercial airplanes




<h1>REFERENCE GOOGLE DATASET</h1>

A Google Reference JSON<sub>1</sub> file is given which contains the Google results for each of the queries in your dataset. The JSON file is structured in the form of a query as the key and a list of 10 results as the value for that key (each a particular URL representing a result). The Google results for a specific query are ordered as they were returned by Google. Namely the <em>1st</em> element in the list represents the top result that was scraped from Google, the <em>2nd</em> element represents the second result, and so on. Example:




1 JSON, JavaScript object Notation is a file format used to transmit data objects consisting of key-value pairs. It is programming language independent. <a href="https://www.softwaretestinghelp.com/json-tutorial/">https://www.softwaretestinghelp.com/json</a><a href="https://www.softwaretestinghelp.com/json-tutorial/">–</a><a href="https://www.softwaretestinghelp.com/json-tutorial/">tutorial/</a>




{

“A two dollar bill from 1953 is worth what”: [

“http://www.antiquemoney.com/old-two-dollar-bill-value-price-guide/two-dollarbank-notes-pictures-prices-history/prices-for-two-dollar-1953-legal-tenders/”,

“https://oldcurrencyvalues.com/1953_red_seal_two_dollar/”,

“https://www.silverrecyclers.com/blog/1953-2-dollar-bill.aspx”,

“https://www.ebay.com/b/1953-A-2-Dollar-Bill/40033/bn_7023293545”,

“https://www.ebay.com/b/1953-2-US-Federal-Reserve-SmallNotes/40029/bn_71222817”,

“https://coinsite.com/why-the-1953-2-dollar-bill-has-a-red-seal/”,

“https://hobbylark.com/collecting/Value-of-Two-Dollar-Bills”,

“https://www.quora.com/What-is-the-value-of-a-2-dollar-bill-from-1953”,

“https://www.reference.com/hobbies-games/1953-2-bill-worth-c778780b24b9eb8a”,

“https://treasurepursuits.com/1953-2-dollar-bill-value-whats-it-worth/”

]

}

<h1>DETERMINING OVERLAP AND CORRELATION</h1>




<em>Overlap</em>: Since the Google results are taken as our baseline, it will be interesting to see how many identical results are returned by your assigned search engine, regardless of their position.

Assuming Google’s results are the standard of relevance, the percentage of identical results will act as a measure of the quality of your assigned search engine.




Each of the queries in your dataset should be run on your assigned search engine. You should capture the top ten results. Only the resulting URL is required. For each of the top ten results for each query you should compute an overlap score between our reference Google dataset and your scraped results. The output format is described ahead.




<strong>Note</strong>: If you get less than 10 URLs for a particular query, you can just use those results to compare against Google results. For example: if a query gets 6 results from a search engine, just use those 6 results to compare against 10 results of Google reference dataset and produce statistics for that particular query.




<em>Correlation</em>: In statistics, <strong>Spearman’s rank correlation coefficient</strong> or <strong>Spearman’s rho</strong>, is a measure of the statistical dependence between the rankings of two variables. It assesses how well the relationship between two variables can be described. Intuitively, the Spearman correlation between two variables will be high when observations have a similar rank, and low when observations have a dissimilar rank.

The rank coefficient <em>r</em><em>s</em> can be computed using the formula




where,

<ul>

 <li><em>d</em><em>i</em> is the difference in the two rankings, and</li>

 <li><em>n</em> is the number of observations</li>

</ul>

<strong> </strong>

<strong>Note: </strong>The formula above when applied to search results yields a somewhat modified set of values that can be greater than one or less than minus one. However the sign of the Spearman correlation indicates the direction of association between the two rank variables. If the rank of one is near the rank of the other, then the Spearman correlation value is positive. If the rank of one is dissimilar to the rank of the other, then the Spearman correlation value will be negative.

<strong> </strong>

<strong> </strong>

<strong>Note</strong>: In the event that your search engine account enables personalized search, please turn this off before performing your tests.

<strong> </strong>

<strong> </strong>

<h1>Example1.1: “Who discovered x-rays in 1885”</h1>

<strong> </strong>

<strong> </strong>

<h1>GOOGLE RESULTS</h1>

<ol>

 <li>https://explorable.com/wilhelm-conrad-roentgen</li>

 <li>https://www.the-scientist.com/foundations/the-first-x-ray-1895-42279</li>

 <li>https://www.bl.uk/learning/cult/bodies/xray/roentgen.html</li>

 <li>https://en.wikipedia.org/wiki/Wilhelm_R%C3%B6ntgen</li>

 <li>https://www.wired.com/2010/11/1108roentgen-stumbles-x-ray/</li>

 <li>https://www.history.com/this-day-in-history/german-scientist-discovers-x-rays</li>

 <li>https://www.aps.org/publications/apsnews/200111/history.cfm</li>

 <li>https://www.nde-ed.org/EducationResources/CommunityCollege/Radiography/Introduction/history.htm</li>

 <li>https://www.dw.com/en/x-ray-vision-an-accidental-discovery-that-revolutionized-medicine/a-18833060</li>

 <li>http://www.slac.stanford.edu/pubs/beamline/25/2/25-2-assmus.pdf</li>

</ol>

<strong> </strong>

<h1>RESULTS FROM ANOTHER SEARCH ENGINE</h1>

<ol>

 <li>https://explorable.com/wilhelm-conrad-roentgen</li>

 <li>https://www.history.com/this-day-in-history/german-scientist-discovers-x-rays</li>

 <li>https://www.coursehero.com/file/p5jkhl/Discovery-of-X-rays-In-1885-Wilhem-Rontgen-while-studying-the-characteristics/</li>

 <li>http://www.nde-ed.org/EducationResources/HighSchool/Radiography/discoveryxrays.htm</li>

 <li>https://www.answers.com/Q/Who_discovered_x-rays</li>

 <li>https://www.aps.org/publications/apsnews/200111/history.cfm</li>

 <li>https://www.answers.com/Q/Who_discovered_x-rays</li>

 <li>https://www.coursehero.com/file/p5jkhl/Discovery-of-X-rays-In-1885-Wilhem-Rontgen-while-studying-the-characteristics/</li>

 <li>https://www.wired.com/2010/11/1108roentgen-stumbles-x-ray/</li>

 <li>http://time.com/3649842/x-ray/</li>

</ol>

<strong> </strong>

<h1>RANK MATCHES FROM GOOGLE AND ANOTHER SEARCH ENGINE</h1>

1 AND 1

<ul>

 <li>AND 9</li>

 <li>AND 2</li>

 <li>AND 6</li>

 <li>AND 4</li>

</ul>

<strong> </strong>

<strong>We are now ready to compute Spearman’s rank correlation coefficient.</strong>

<table width="312">

 <tbody>

  <tr>

   <td width="88"><strong>Rank Google </strong></td>

   <td width="80"><strong>Rank </strong><strong>Other Srch Engine </strong></td>

   <td width="70"><strong><em>d</em></strong><strong><em>i</em></strong></td>

   <td width="73"><strong><em>d</em></strong><strong><em>i2</em></strong></td>

  </tr>

  <tr>

   <td width="88"><strong>1 </strong></td>

   <td width="80"><strong>1 </strong></td>

   <td width="70"><strong>0 </strong></td>

   <td width="73"><strong>0 </strong></td>

  </tr>

  <tr>

   <td width="88"><strong>5 </strong></td>

   <td width="80"><strong>9 </strong></td>

   <td width="70"><strong>-4 </strong></td>

   <td width="73"><strong>16 </strong></td>

  </tr>

  <tr>

   <td width="88"><strong>6 </strong></td>

   <td width="80"><strong>2 </strong></td>

   <td width="70"><strong>4 </strong></td>

   <td width="73"><strong>16 </strong></td>

  </tr>

  <tr>

   <td width="88"><strong>7 </strong></td>

   <td width="80"><strong>6 </strong></td>

   <td width="70"><strong>1 </strong></td>

   <td width="73"><strong>1 </strong></td>

  </tr>

  <tr>

   <td width="88"><strong>8 </strong></td>

   <td width="80"><strong>4 </strong></td>

   <td width="70"><strong>4 </strong></td>

   <td width="73"><strong>16 </strong></td>

  </tr>

 </tbody>

</table>

<strong> </strong>

<h2>The sum of <em>d</em><em>i2</em> = 49. The value of n = 5. Substituting into the equation</h2>

<strong> </strong>

<strong> </strong>

<h2>1 – ( (6 * 49) / (5 * 24) ) = 1 – ( 294/120) = 1 – 2.45 = -1.45</h2>




Even though we have five overlapping results (50% overlap), their positions in the search result list produce a negative Spearman coefficient indicating that the overlapping results are uncorrelated. Clearly the two search engines are using different algorithms for weighting and ranking the documents they determine are most relevant to the query. Moreover their algorithms are emphasizing different ranking features.




<strong>Note</strong>: the value of <strong><em>n</em></strong> in the equation above refers to the number of URL matches (in this case, five) and does not refer to the original number of results (in this case, ten).

<strong> </strong>

<h1>TASKS Task1: Scraping results from your assigned search engine</h1>

<strong> </strong>

In this task you need to develop a script (computer program) that could scrape the top 10 results from your assigned search engine. You may use any language of your choice. <strong>Always incorporate random delay between 10 to 100 seconds while scraping multiple queries, else you may be blocked off by the search engine and they may not allow you to scrape results for several hours.</strong> For reference:




<ul>

 <li><a href="https://pypi.org/project/beautifulsoup4">https://pypi.org/project/beautifulsoup4</a><a href="https://pypi.org/project/beautifulsoup4">,</a> a python library for parsing HTML documents ● URLs for the search engines:

  <ul>

   <li>Bing: <a href="https://www.bing.com/search?q=">http://www.bing.com/search?q=</a></li>

  </ul></li>

</ul>

○ Yahoo!: <a href="http://www.search.yahoo.com/search?p=">http://www.search.yahoo.com/search?p=</a>

○ Ask: <a href="https://www.ask.com/web?q=">http://www.ask.com/web?q=</a>

○ Teoma: <a href="https://www.teoma.com/web?q=">https://www.teoma.com/web?q=</a>

For each URL, you can add your query string after q=




<ul>

 <li>Selectors for various search engines, you grab links by looking for href in these selectors:

  <ul>

   <li>Bing: [“li”, attrs = {“class” : “b_algo”}]</li>

  </ul></li>

</ul>

○ Yahoo!: [“a”, attrs = {“class” : “ac-algo fz-l ac-21th lh-24”}]

○ Ask: [“div”, attrs = {“class” : “PartialSearchResults-item-title”}] ○ Teoma: [“a”, attrs = {“class” : “algo-title”}]




By executing this task you need to generate a JSON file which will store your results in the JSON format described above and repeated here.




{

Query1: [Result1, Result2, Result3, Result4, Result5, Result6, Result7, Result8, Result9, Result10],

Query2: [Result1, Result2, Result3, Result4, Result5, Result6, Result7, Result8, Result9, Result10],

….

Query100: [Result1, Result2, Result3, Result4, Result5, Result6, Result7, Result8, Result9, Result10]

}




Here Result1 is the top result for that particular query.




<h1>Task2: Determining the Percent Overlap and the Spearman Coefficient</h1>

<strong> </strong>

For this task, you need to use the JSON file that you generated in Task 1 and the Google reference dataset which is provided by us and compare the results as shown in the <strong>Determining Correlation</strong> section above. The output should be a <strong>CSV</strong> file with the following information:




<ol>

 <li>Use the JSON file that you generated in Task 1 and do the following steps on each query:</li>

 <li>Determine the URLs that match with the given reference Google dataset, and their position in the search engine result list</li>

 <li>Compute the percent of overlap. In Example1.1, above the percent overlap is 5/10 or 50%.</li>

 <li>Compute the Spearman correlation coefficient. In above Example1.1, the coefficient is -1.45.</li>

 <li>Once you run all of the queries, collect all of the top ten URLs and compute the statistics, as shown in the following example:</li>

</ol>




<strong> </strong>

<strong>Note</strong>: The above example is a table with four columns, rows containing results for each of the queries, and averages for each of the columns. Of course the actual values above are only for demonstration purposes.  <strong> </strong>

<strong>Points to note: </strong>

<ul>

 <li>Always incorporate a delay while scraping. We recommend that you use a random delay with a range of 10 to 100 seconds.</li>

 <li>You will likely be blocked off from the search engine if you do not implement some delay in your code.</li>

 <li>You should ignore the People Also Ask boxes and any carousels that may be included in the results.</li>

</ul>

<strong> </strong>

<h1>SAMPLE SCRAPING PROGRAM IN PYTHON</h1>

Here is a program you can use to help you get started




from bs4 import BeautifulSoup from time import sleep import requests from random import randint from html.parser import HTMLParser




USER_AGENT = {‘User-Agent’:’Mozilla/5.0 (Windows NT 10.0; Win64; x64)

AppleWebKit/537.36 (KHTML, like Gecko) Chrome/61.0.3163.100

Safari/537.36′}

class SearchEngine:     @staticmethod     def search(query, sleep=True):

if sleep: # Prevents loading too many pages too soon             time.sleep(randint(10, 100))

temp_url = ‘+’.join(query.split()) #for adding + between words for the query

url = ‘SEARCHING_URL’ + temp_url

soup = BeautifulSoup(requests.get(url, headers=USER_AGENT).text,

“html.parser”)

new_results = SearchEngine.scrape_search_result(soup)         return new_results




@staticmethod     def scrape_search_result(soup):

raw_results = soup.find_all(“SEARCH SELECTOR”)         results = []

#implement a check to get only 10 results and also check that URLs must not be duplicated         for result in raw_results:             link = result.find(‘a’).get(‘href’)             results.append(link)         return results




#############Driver code############

SearchEngine.search(“QUERY”)

####################################




<h1>FAQs</h1>

<ol>

 <li>What do I need to run Python on my Windows/Mac machine?</li>

</ol>

You can refer to the documentation for setup: <a href="https://docs.python.org/3.6/using/index.html">https://docs.python.org/3.6/using/index.html</a>

We encourage you to use Python 3.6. You can find many tutorials on Google.

<ol start="2">

 <li>Given that Python is installed what lines of the sample program do I have to modify to get it to work on a specific search engine?</li>

</ol>

In the reference code, you need to:

<ul>

 <li>Supply in query variable</li>

 <li>Change SEARCHING_URL and SEARCH SELECTOR as per the search engine that is assigned to you</li>

 <li>Implement the code that extracts only top 10 URLs and make sure that none of them is repeated</li>

 <li>Implement the main function</li>

</ul>

<ol start="3">

 <li>What to do if the query does not produce ten results.</li>

</ol>

You can modify the URLs to get 30 results on single page:

<ul>

 <li>For bing use count=30 – <a href="https://urldefense.proofpoint.com/v2/url?u=http-3A__www.bing.com_search-3Fq-3Dtest-26count-3D30&amp;d=DwMFaQ&amp;c=clK7kQUTWtAVEOVIgvi0NU5BOUHhpN0H8p7CSfnc_gI&amp;r=5nz01Hxlw4vO4-NAa0g_Sg&amp;m=x0a8f8E4SQyqffSaHwmuNnLOGqbX_lam7GsvpiIe9J8&amp;s=SyypktcKO3QJvImLwt0Gbf_awbVTkZ0oanKS7A7ML7E&amp;e=">http://www.bing.com/search?q=test&amp;count=30</a></li>

 <li>For yahoo use n=30 – <a href="https://urldefense.proofpoint.com/v2/url?u=https-3A__search.yahoo.com_search-3Fp-3Dtest-26n-3D30&amp;d=DwMFaQ&amp;c=clK7kQUTWtAVEOVIgvi0NU5BOUHhpN0H8p7CSfnc_gI&amp;r=5nz01Hxlw4vO4-NAa0g_Sg&amp;m=x0a8f8E4SQyqffSaHwmuNnLOGqbX_lam7GsvpiIe9J8&amp;s=O4vSNyzgpJfZEd1zg4aOeagHm-H_6gq6XHlETe4YJvo&amp;e=">https://search.yahoo.com/search?p=test&amp;n=30</a></li>

 <li>For Ask and Teoma there does not appear to be a parameter which could produce n results on single page, so instead you can update the URL in such a manner which increments page number</li>

 <li>For Ask use page=2 – <a href="https://urldefense.proofpoint.com/v2/url?u=https-3A__www.ask.com_web-3Fq-3Dtestn-26page-3D2&amp;d=DwMFaQ&amp;c=clK7kQUTWtAVEOVIgvi0NU5BOUHhpN0H8p7CSfnc_gI&amp;r=5nz01Hxlw4vO4-NAa0g_Sg&amp;m=x0a8f8E4SQyqffSaHwmuNnLOGqbX_lam7GsvpiIe9J8&amp;s=UFByPhUwx0shdxT0bwCldSNKID4e3-e2YbJEvuSFdlA&amp;e=">https://www.ask.com/web?q=testn&amp;page=2</a></li>

 <li>For Teoma use page=2 – <a href="https://urldefense.proofpoint.com/v2/url?u=https-3A__www.teoma.com_web-3Fq-3Dtest-26page-3D2&amp;d=DwMFaQ&amp;c=clK7kQUTWtAVEOVIgvi0NU5BOUHhpN0H8p7CSfnc_gI&amp;r=5nz01Hxlw4vO4-NAa0g_Sg&amp;m=x0a8f8E4SQyqffSaHwmuNnLOGqbX_lam7GsvpiIe9J8&amp;s=jdOqwh1LWG5Ueyg7lcuFIYd6JfNGBXC1rd6rW74XdIw&amp;e=">https://www.teoma.com/web?q=test&amp;page=2</a></li>

</ul>

<ol start="4">

 <li>Two URLs that differ only in the scheme (http versus https) can be treated as the same.</li>

 <li>Metrics for similar URLs:

  <ol>

   <li>As browsers default to www when no host name is provided, so xyz.com is identical to www.xyz.com</li>

   <li>URLs that only differ in the scheme (http or https) are identical</li>

   <li>xyz.com and www.xyz.com/ – You need to remove slash(/) at the end of</li>

  </ol></li>

</ol>

URL

<ol>

 <li>Convert all URLs to lowercase, www.xyz.com/ab and <a href="http://www.xyz.com/Ab">xyz.com/Ab</a><a href="http://www.xyz.com/Ab">.</a></li>

</ol>

<ol start="6">

 <li>Value of rho:

  <ol>

   <li>If no overlap, rho = 0</li>

   <li>If only one result matches:</li>

   <li>if Rank in your result = Rank in Google result → rho=1 ii. if Rank in your result ≠ Rank in Google result → rho=0</li>

  </ol></li>

 <li>Rho value may be extremely large/small

  <ol start="100">

   <li>In some cases the value may &gt;100 or &lt;-100. We just accept the value and calculate the average like nothing happens</li>

   <li>How to calculate average rho? We calculate rho for each query and sum them up. Then we get the average</li>

  </ol></li>

 <li>Save order as JSON</li>

 <li>You can save the dictionary in python as JSON directly by importing json library calling json.dump(args)</li>

</ol>


