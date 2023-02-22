# DatePicker
For full documentation and customization notes refer to [react-aria](https://react-spectrum.adobe.com/react-aria/useDatePicker.html)

# Features
- Drop down menu to select year and month
- Days outside of month are diabled and greyed out
- Year range from +/- 80 years of current year selected
- Can type in date manually or press button to open dialog menu
- Displays date in format MM/DD/YYYY

# Dev Dependencies
- react-aria
- react-stately
- date-fns

# Getting Started
Refer to [react-aria](https://react-spectrum.adobe.com/react-aria/useDatePicker.html) for full documentation of use cases
```jsx
import { useState } from 'react';
import { DatePicker } from 'components/datePicker/DatePicker';
import { today, parseDate, getLocalTimeZone } from '@internationalized/date';

export default function App() {
  const [value, setValue] = useState(parseDate('1980-01-01'));
  return (
    <div className="flex flex-col justify-center items-center mt-24 text-gray-700">
      <h2 className="mb-2 font-bold text-xl text-left">DatePicker</h2>
      <DatePicker
        value={value}
        onChange={setValue}
        maxValue={today(getLocalTimeZone())}
      />
      <div className="mt-5">Year: {value.year}</div>
      <div>Month: {value.month}</div>
      <div>Day: {value.day}</div>
    </div>
  );
}
```
In the example listed above, we start off with a default date of January 1, 1980 with no min dates set and a max date of today. 

This will return an object with the following properties:
- calendar (str - type of calendar)
- day (int)
- era (str)
- month (int)
- year (int)

## Folder structure
```bash
├── Button -> opening dialog
├── Calendar -> container
├── CalendarCell -> styling of each day
├── CalendarGrid -> styling of each week
├── DateField -> how the date appears to the user
├── DatePicker -> import this component
├── Dialog
└── Popover
```

# Known Errors
- Will not work when React Strict Mode is enabled, remove on App.js

# Potential feaatures to be added
- Display dates in multiple forms (currently can only display in MM/DD/YYYY)
