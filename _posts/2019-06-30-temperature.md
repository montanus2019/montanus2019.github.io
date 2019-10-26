---

layout: post

title:  体感温度计算公式

tags:

- 气象

---

* 目录
{:toc}

## 1958

1958年，美国的Paul Siple曾就风对人体的热流失成正比例这种说法,根据当时计算风寒指数的公式，简化出以下的一条算式：

$$lT=T-2\times\sqrt{V}$$

(旧)体感温度(°C)=温度(°C)-2√风速(米/每秒)。

## 1984

1984年，罗伯特·史特德曼（Robert G. Steadman）发表《体感温度的通用公式》（A universal scale of apparent temperature）如下：

$$AT=1.07T+0.2e-0.65V-2.7$$
$$e=\frac{RH}{100}\times{6.105}\times\exp{\frac{17.27T}{237.7+T}}$$

其中AT为体感温度（°C）、T为气温（°C）、e为水汽压（hPa）、V为风速（m/sec）、RH为相对湿度（%）。

## 1990

The Heat Index Equation

The computation of the heat index is a refinement of a result obtained by multiple regression analysis carried out by Lans P. Rothfusz and described in a 1990 National Weather Service (NWS) Technical Attachment (SR 90-23).  The regression equation of Rothfusz is

$$HI = -42.379 + 2.04901523*T + 10.14333127*RH - .22475541*T*RH - .00683783*T*T - .05481717*RH*RH + .00122874*T*T*RH + .00085282*T*RH*RH - .00000199*T*T*RH*RH$$

where T is temperature in degrees F and RH is relative humidity in percent.  HI is the heat index expressed as an apparent temperature in degrees F.  If the RH is less than 13% and the temperature is between 80 and 112 degrees F, then the following adjustment is subtracted from HI:
$$ADJUSTMENT = [(13-RH)/4]*SQRT{[17-ABS(T-95.)]/17}$$

where ABS and SQRT are the absolute value and square root functions, respectively.  On the other hand, if the RH is greater than 85% and the temperature is between 80 and 87 degrees F, then the following adjustment is added to HI:
$$ADJUSTMENT = [(RH-85)/10] * [(87-T)/5]$$

The Rothfusz regression is not appropriate when conditions of temperature and humidity warrant a heat index value below about 80 degrees F. In those cases, a simpler formula is applied to calculate values consistent with Steadman's results:
$$HI = 0.5 * {T + 61.0 + [(T-68.0)*1.2] + (RH*0.094)}$$

In practice, the simple formula is computed first and the result averaged with the temperature. If this heat index value is 80 degrees F or higher, the full regression equation along with any adjustment as described above is applied.

The Rothfusz regression is not valid for extreme temperature and relative humidity conditions beyond the range of data considered by Steadman.

## jianshu

看了下 NOAA 的http://www.wpc.ncep.noaa.gov/html/heatindex.shtml这个链接，计算体感温度的。看了下计算方法，是简单的公式，就是没有看公式是怎么得出来的。写成python大概这样子。

```python
import math
def calc_heat_index(T, RH):
    '''NOAA计算体感温度 参数为气温(摄氏度)和相对湿度(0~100或者0~1)'''
    if RH < 1:
        RH *= 100
    T = 1.8 * T + 32
    HI = 0.5 * (T + 61 + (T - 68) * 1.2 + RH * 0.094)
    if HI >= 80:  # 如果不小于 80华氏度 则用完整公式重新计算
        HI = -42.379 + 2.04901523 * T + 10.14333127 * RH - .22475541 * T * RH \
             - .00683783 * T * T - .05481717 * RH * RH + .00122874 * T * T * RH \
             + .00085282 * T * RH * RH - .00000199 * T * T * RH * RH
        if RH < 13 and 80 < T < 112:
            ADJUSTMENT = (13 - RH) / 4 * math.sqrt((17 - abs(T - 95)) / 17)
            HI -= ADJUSTMENT
        elif RH > 85 and 80 < T < 87:
            ADJUSTMENT = (RH - 85) * (87 - T) / 50
            HI += ADJUSTMENT
    return round((HI - 32) / 1.8, 2)

```
本文共{{ page.content | strip_html | strip_newlines | split: "" | size }}字。

