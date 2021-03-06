# FSCalendar

## Features
### 1. Easy appearance adjustment
![appearance](https://cloud.githubusercontent.com/assets/5186464/6208969/20ee842a-b5fb-11e4-8875-132d42893b9e.png)

### 2. Subtitle
![subtitle1](https://cloud.githubusercontent.com/assets/5186464/6209081/54d8a4cc-b5fc-11e4-981e-d4bb21a45628.png)

## Usage

To run the example project, clone the repo, and run `pod install` from the Example directory first.

### 1. Simple DataSource/Delegate Pattern (IBOutlet supported)
    _calendar.dataSource = self; 
    _calendar.delegate = self;
    
#### FSCalendarDataSource
- (NSString *)calendar:(FSCalendar *)calendar subtitleForDay:(NSDate *)date; // set subtitle
- (BOOL)calendar:(FSCalendar *)calendar hasEventForDate:(NSDate *)date; // set event dot

#### FSCalendarDelegate
- (BOOL)calendar:(FSCalendar *)calendar shouldSelectDate:(NSDate *)date;
- (BOOL)calendar:(FSCalendar *)calendar didSelectDate:(NSDate *)date;
- (void)calendarCurrentMonthDidChange:(FSCalendar *)calendar;
    
### 2. Page Direction Supported
    _calendar.flow = FSCalendarFlowVertical; //Change to vertical flow, default is FSCalendarFlowHorizontal
    
### 3. Flexible Appearance Customization
    [[FSCalendar appearance] setWeekdayTextColor:[UIColor redColor]];   // week symbol color
    [[FSCalendar appearance] setHeaderTitleColor:[UIColor darkGrayColor]]; // header text color
    [[FSCalendar appearance] setEventColor:[UIColor greenColor]]; // event mark color
    [[FSCalendar appearance] setSelectionColor:[UIColor blueColor]]; // selection fill color
    [[FSCalendar appearance] setHeaderDateFormat:@"yyyy-MM"]; // header date format
    [[FSCalendar appearance] setMinDissolvedAlpha:0.5]; // change to 1.0 to make header no alpha
    [[FSCalendar appearance] setTodayColor:[UIColor redColor]]; // today fill color
    [[FSCalendar appearance] setUnitStyle:FSCalendarUnitStyleCircle]; // shape of today/selection fill color.Circle/Fectangle
    
### 4. Header (IBOutlet supported)
    FSCalendarHeader *header = [[FSCalendarHeader alloc]    initWithFrame:CGRectMake(0,0,_calendar.frame.size.width,_calendar.frame.size.height)];
    _calendar.header = header;

## Requirements
ios 7.0

## Installation

FSCalendar is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

    pod "FSCalendar"

## Author

Wenchao Ding, f33chobits@gmail.com

## License

FSCalendar is available under the MIT license. See the LICENSE file for more info.

