**Summary**
This Android app provides a platform for stocks trading, including, features such as searching company stock details, buying/selling stocks, keeping track of stock porfolio/favorites, viewing stock SMA charts and news, allowing sharing news on twitter for a given stock. Custom Nodejs backend deployed using GCP is used for all API calls. The backend uses Tingo API for all stock related data, and News API for displaying stock related news. Highcharts is used for displaying the SMA chart data for a given ticker.
**Java File descriptions**
ApiCall.java: the class that allows making api GET requests using Volley
AutoSuggestApdapter.java: Adpater used for autocomplete search feature.
Company.java: used to create a Company object that includes the company name, ticker, number of company shares owned, last company price, price change,
 News.java: used to create a news object that will be used to display the list of news related to given stock
CompanyHeaderViewHolder.java: the header view holder for the sectioned RecyclerView in home page. Currently we only have two sections portfolio and favorites.
CompanyItemViewHolder.java: item view holder for a given section of RecyclerView. This is used to display the company information inside either portfolio or favorites
CustomDividerItemDecoration.java: extends the DividerItemDecoration class for adding vertical lines between items in RecyclerView
CustomGridAdapter.java: extends base adpater for storing company price summary details (such as last price, previous close, volume, bid size, etc) to be displayed using gridView
CustomNewsAdapter.java: extends RecyclerView.Adapter<CustomNewsAdapter.ViewHolder> for storing a list of all news articles related for a given stock. Also contains the ViewHolder class extention of RecyclerView.ViewHolder to be used to display these news item inside a RecyclerView
MainActivity.java: extends AppCompatActivity. The main activity of the app that acts as the home page of the app. Home page contains toolbar for searching stocks, the current date, Networth of all the stocks plus excess cash (the app starts with 20,000 cash and no stocks), and portfolio and favorites section.
DetailsActivity.java: extends AppCompatActivity. This is the stock details activity that is reached once the user clicks search icon in home page(the main activity) for a selected stock, or clicks on the company item in either protfolio or favorite section of home page. Contains stock summary, price details, options for trading this stock, and viewing stock related news article.
FavoriteSection.java: extends io.github.luizgrp.sectionedrecyclerviewadapter.Section 3rd party Android library to create favorites section inside the home page Recyclerview
PortfolioSection.java: extends io.github.luizgrp.sectionedrecyclerviewadapter.Section 3rd party Android library to create portfolio section inside the home page Recyclerview
ItemMoveCallback.java: extends ItemTouchHelper.Callback to allow rearranging the positions of company items inside portfolio or favorites section
 SwipeToDeleteCallback.java; extends ItemTouchHelper.Callback to allow removing stocks/company items from favorites sections only.
LocalStorage.java: class used to manage the company data stored in the SharedPreferences. This is used to keep track of all the company items inside either portfolio section or favorites section so if user restarts the app, the stock inside portoflio or favorites section are not lost. Reinstalling the app will however, clear the local storage (SharedPreferences)
SplashActivity.java: the very first activity that runs when the app is load. It display the app logo until the home page is loaded
