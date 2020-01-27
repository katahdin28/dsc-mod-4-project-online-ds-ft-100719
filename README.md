
# Module 4 -  Final Project Specifications

Goal: Identify 5 zip codes for maximum investment returns in the San Francisco Bay Area

Results:
We have identified 5+ zip codes in the San Francisco Bay Area that have the highest predicted percentage housing price growth over the nest two years. The analysis is based on more than 20 years of housing price index data from Zillow's research team, and relies on an ARIMA regression to forecast housing prices into future months.

We have defined out outcome of interest as the expected value growth percentage in real estate prices for the zipcode.  This metric means that for a given amount of invested dollars, maximizing growth as a percentage of current home price index should return the highest ROIC. However, we will also evaluate downside risk and present it, but will need additional input from the client on their risk aversity.

A summary of the selected zip codes is below:

Zipcode	Forecast 2-Yr Growth	97.5% Lower-Bound 2-Yr Forecast
94572	47 %	-4 %
94043	39 %	17 %
95035	38 %	8 %
94089	31 %	5 %
94063	30 %	1 %
94087	28 %	6 %

Furthermore, we have reviewed a key indicator of buyer/supplier demand ratios using another Zillow-produced metric, the Buyer-Seller Index (BSI), for the two zipcodes within our top 10 highest-growth forecast list. For both of these, the BSI has approximately tracked housing price growth rates over the last 8 years, and for both, the BSI value is at a historical high point currently (8-10 on a scale of 0 to 10). This point supports our analysis based solely on historical price patterns.

We also want to be sensitive to potential downside risk - and as such have included a metric on the lower-bound of the projected housing price growth based on our ARIMA forecast model. For all except the top-growth zipcode, the lower-bound price growth is still positive, and as much as 40% of the expected value growth rate. However, our top-forecast growth zipcode has a slightly negative lower-bound rate, representing more than a 50% swing in housing price. This appears to be a high-variance housing price region, and the client may want to deprioritze this region in favor of lower-variance, also high-growth forecast regions.

One of the primary reasons growth rates are so high for these zipcodes is that the starting average home price value in these zipcodes is low to begin with. Therefore, relatively smaller price increases compared to other zipcodes are resulting in higher percentage growth. This is fine, as our client is looking to maximize growth on a per-dollar basis, rather than a per-unit basis. Based on a survey of the zipcodes, these are smaller, more coastal, non-central areas near either Palo Alto, Berkeley, or other major metro centers that may be finally being more fully penetrated by high-income residents. It may be worth looking into whether there are any idiosyncratic charactaristics of these areas that might imply a price ceiling (e.g waste treatment plants, street accessibility issues, etc.

A limitation of the identified zipcodes is that these are smaller regions, often less than half the size or even a fifth the size of the median zipcode in the region. Therefore, the investment team may need to move further down the list of prioritized regions to find enough potential acquisition targets.

Finally - an important caveat is that our ARIMA model forecasting is highly sensitive to relatively recent upturns or downturns within the last few months of data. We have trained the model on 20+ years of data, which for many zip codes includes several moderate drops or spikes in housing prices (especially circa 2006-2010). A second caveat is that housing prices were very sensitive to a market-wide housing price bubble deflation in the late 00's, and any investor shoudl be concerned about the possibility of a price deflation event that is not predictable from the existing data. However, future work should include pressure-testing each 2-year prediction on data that ends 2-10 months prior to the actual end of data to test for sensitivity to end-of-period trends.

## Key Methods

* ARIMA model from statsmodels.tsa.arima_model

### The Data

Our dataset comes from the [Zillow Research Page](https://www.zillow.com/research/data/). I have also used Zillow's zipcode-level Buyer Seller Index (Cross-Geography) as an alternative demand indicator.