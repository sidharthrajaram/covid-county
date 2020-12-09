<p align="middle">
  <img src="/banner.png" width="100%" />
</p>

## The Endpoint (HTTP GET Request)
### `https://www.plansafe.xyz/api/counties/{county}/{state}`

###### Note: Provide the full names for county and state. For example, "/harris/texas". Also, when providing the county name, you don't need to provide the word "county" after the name of the county.

### Optional query parameters for data from a specific day:
`month (integer)`

`day (integer)`

`year (integer)`
###### Note: If requesting county data for a specific date, be sure to provide all three date parameters. If any of the three are not present, the latest COVID-19 data for the requested county will be returned."


## Data Provided

**FIPS** County FIPS ID

**county** Name of the county

**state** Name of the state

**date** Date at which data was collected (at source)

**fatality_ratio** COVID-19 fatality rate for the county

**per_100k** COVID-19 incidence rate per 100,000 people (scaled for the county)

**total_confirmed_cases** Total confirmed COVID-19 cases in the county

**total_deaths** Total COVID-19 deaths in the county

**active_cases** Current number of active COVID-19 cases in the county.

## Usage Examples
### Python:
```python
import requests
url = "https://www.plansafe.xyz/api/counties/"
county = "harris"
state = "texas"
url = url + county + '/' + state
res = requests.get(url)
res.json()
```
### Javascript:
```javascript
import axios from 'axios'
...
const headers = {
  'Content-Type': 'application/json',
}
    
axios.get(`https://www.plansafe.xyz/api/counties/harris/texas`, { headers: headers})
.then(res => {
  const county_data = res.data;
  console.log(county_data);
})
```
