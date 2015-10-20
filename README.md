# iOS_biji 
```Objective-C 
- (NSString *)timeToTranslate:(int)time
{
    int minutes = 0;
    int seconds = 0;
    minutes = time / 60;
    seconds = time % 60;
    if (minutes == 0) {
        return [NSString stringWithFormat:@"%.2d秒",seconds];
    }
    return [NSString stringWithFormat:@"%.2d分%.2d秒",minutes,seconds];
}


#program - mark 
- (NSString *)getFileSizeString:(NSString *)size
{
    if([size floatValue]>=1024*1024)
    {
        return [NSString stringWithFormat:@"%1.2fM",[size floatValue]/1024/1024];
    }
    else if([size floatValue]>=1024&&[size floatValue]<1024*1024)
    {
        return [NSString stringWithFormat:@"%1.2fK",[size floatValue]/1024];
    }
    else
    {
        return [NSString stringWithFormat:@"%1.2fB",[size floatValue]];
    }
}
```

```Objective-C
#program - mark 时间计算
+(NSString *)GetTomorrowDay:(NSDate *)aDate
{
    NSCalendar *gregorian = [[NSCalendar alloc] initWithCalendarIdentifier:NSChineseCalendar];
    NSDateComponents *components = [gregorian components:NSCalendarUnitYear | NSCalendarUnitMonth |  NSCalendarUnitDay |NSCalendarUnitHour |NSCalendarUnitMinute |NSCalendarUnitSecond fromDate:aDate];
    [components setHour:[components hour]-1];
    NSDate *beginningOfWeek = [gregorian dateFromComponents:components];
    NSDateFormatter *dateday = [[NSDateFormatter alloc] init];
    [dateday setDateFormat:@"yyyy-MM-dd HH:mm:ss"];
    return [dateday stringFromDate:beginningOfWeek];
}
```
