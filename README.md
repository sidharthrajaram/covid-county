<p align="middle">
  <img src="/banner.png" width="100%" />
</p>

## The Endpoint (HTTP GET Request)
### `https://www.plansafe.xyz/api/counties/us/{state}/{county}`

#### Note: Provide the full names for county and state. For example, "/texas/harris". 

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

## Data Sources

<a href="https://github.com/CSSEGISandData/COVID-19">Johns Hopkins University Center for Systems Science and Engineering</a>

## Usage Examples
### Python:
```python
import requests
url = "https://www.plansafe.xyz/api/counties/us/"
county = "harris"
state = "texas"
url = url + state + '/' + county
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
    
axios.get(`https://www.plansafe.xyz/api/counties/us/texas/harris`, { headers: headers})
.then(res => {
  const county_data = res.data;
  console.log(county_data);
})
```
