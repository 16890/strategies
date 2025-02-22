
> Name

逐日缠绕分心线量化策略SSL-Hybrid-Exit-Arrow-Quant-Strategy

> Author

ChaoZhang

> Strategy Description

![IMG](https://www.fmz.com/upload/asset/11d68ec62d6f09f2b8d.png)
[trans]

## 概述

逐日缠绕分心线量化策略是一种基于均线和最大最小价指标的短线量化交易策略。它利用SSL混合指标的EXIT箭头来判断买卖点,配合QQE指标进行过滤,采用ATR指标计算止损位和分批加仓位。该策略适合对市场波动敏感且风险控制严格的投资者。

## 策略原理

该策略使用SSL混合指标的EXIT箭头判断买卖入场点。EXIT箭头上方为EXIT高点,下方为EXIT低点。当收盘价从EXIT高点向下穿过时产生卖出信号,当收盘价从EXIT低点向上穿过时产生买入信号。

为了提高信号的可靠性,该策略引入QQE指标作为辅助过滤条件。EXIT箭头产生的信号只有在QQE指标同方向时才会执行。

为控制风险,该策略使用倍数ATR指标计算止损位和分批加仓位。空头止损为收盘价+ATR×1.8,多头止损为收盘价-ATR×1.8。分三批加仓,每批加仓金额为初始金额的10%,加仓位分别为收盘价-ATR×0.1、收盘价-ATR×0.3和收盘价-ATR×0.7。 

每批加仓设置了分别止损,首批金额20%的仓位在达到止损位时止损,其余仓位继续持有。

## 策略优势

1. 通过EXIT箭头获利,及时止损,有效控制风险
2. QQE指标过滤,提高信号的准确性
3. 利用ATR指标根据市场波动情况计算止损和加仓位,风控更加精准
4. 分批加仓,充分把握趋势获利

## 策略风险

1. 盈利仓位达到部分止损可能使剩余仓位面临继续止损的风险。可以考虑整体止盈或股票本体基本面止盈。
2. EXIT箭头和QQE指标对市场波动的敏感性不同,可能产生矛盾信号,应调整参数减少信号冲突。
3. 加仓过于激进容易出现追高杀跌的情况。应审时度势,降低杠杆水平。

## 优化方向

1. 结合股票本体基本面指标进行止盈,例如对账面价值比、市盈率和股息率等设置合理的止盈位。
2. 调整QQE指标的参数,使其与EXIT箭头产生的信号保持一致。
3. 根据市场热度降低加仓比例,在震荡行情中减少加仓。
4. 根据最大回撤、盈亏比等指标测试最佳参数组合。

## 总结
该策略以SSL混合指标的EXIT箭头为信号核心,利用QQE指标和ATR指标进行过滤和止损。通过分批加仓实现盈利放大。是一种短线量化策略,适合于追踪市场短期趋势的情况。该策略具有回撤控制和风险控制能力,但也需要注意防范信号冲突、追高杀跌等风险。如果能够结合股票基本面的止盈方法,在判断市场震荡和调整加仓比例时更为审慎,则该策略的盈利空间将更大。

|| 

## Overview  

The SSL Hybrid Exit Arrow Quant Strategy is a short-term quantitative trading strategy based on moving averages and maximum/minimum price indicators. It utilizes the EXIT arrows of the SSL hybrid indicator to determine entry and exit points, with the QQE indicator as a filter, and calculates stop loss and add-on positions with the ATR indicator. This strategy suits investors who are sensitive to market volatility and have strict risk control.

## Strategy Logic  

This strategy uses the EXIT arrows of the SSL hybrid indicator to determine entry points. Above the EXIT arrows are the EXIT high points, and below them are the EXIT low points. A sell signal is generated when the close price crosses below the EXIT high point, and a buy signal is generated when the close price crosses above the EXIT low point.

To improve signal reliability, the QQE indicator is introduced as an auxiliary filter condition. Signals generated by the EXIT arrows are only executed when the QQE indicator is in the same direction.

To control risks, this strategy uses ATR multiples to calculate stop loss and add-on positions. The stop loss for short positions is close price + ATR × 1.8. The stop loss for long positions is close price – ATR × 1.8. Positions are added in three batches, with the amount of each batch being 10% of the initial amount. The add-on price levels are: close price – ATR × 0.1, close price – ATR × 0.3, and close price – ATR × 0.7.

Each batch of add-on positions has its own stop loss. The first batch of 20% of position size will stop loss when reaching the stop loss level, while the remaining positions continue to hold.

## Advantages  

1. Profit from EXIT arrows and effectively control risks with timely stop loss
2. The QQE filter improves signal accuracy  
3. Use the ATR indicator to calculate dynamic stop loss and add-on positions based on market volatility for more precise risk control
4. Take full advantage of trends through batched add-on positions  

## Risks

1. Partial stop loss of profitable positions may expose the remaining positions to further stop loss. Consider overall profit taking or fundamentals-based stop loss.  
2. Differences in sensitivity to market volatility between EXIT arrows and QQE may cause conflicting signals. Parameters should be adjusted to reduce signal conflicts.
3. Overly aggressive add-on positions are prone to chasing tops and dumping bottoms. Positions sizes should match market conditions.  

## Optimization Directions  

1. Incorporate fundamental indicators like P/B ratio, P/E ratio and dividend yield for fundamentals-based profit taking levels.
2. Adjust QQE parameters to align signals with EXIT arrows.
3. Reduce add-on ratios based on market sentiment in ranging markets.  
4. Test optimum parameter sets based on max drawdown, risk-reward ratios etc.

## Summary
This strategy uses the EXIT arrows of the SSL hybrid indicator as the signal core, with the QQE and ATR indicators as filters and for stop loss. Profit compounding is achieved through batched add-on positions. It is a short-term quantitative strategy suitable for tracking short-term market trends. The strategy has drawdown control and risk mitigation capabilities, but risks like signal conflicts and chasing tops/smashing bottoms should be noted. Incorporating fundamentals-based profit taking and being more prudent when determining oscillating markets and reducing add-on ratios can further expand this strategy’s profit potential.

[/trans]

> Strategy Arguments



|Argument|Default|Description|
|----|----|----|
|v_input_27|6|RSI Length|
|v_input_28|5|RSI Smoothing|
|v_input_29|3|Fast QQE Factor|
|v_input_30|3|Thresh-hold|
|v_input_31_close|0|RSI Source: close|high|low|open|hl2|hlc3|hlcc4|ohlc4|
|v_input_32|50|Bollinger Length|
|v_input_33|0.35|BB Multiplier|
|v_input_34|6|RSI Length|
|v_input_35|5|RSI Smoothing|
|v_input_36|1.61|Fast QQE2 Factor|
|v_input_37|3|Thresh-hold|
|v_input_38_close|0|RSI Source: close|high|low|open|hl2|hlc3|hlcc4|ohlc4|
|v_input_1|true|(?SSL Hybrid Indicator Settings)Show Baseline|
|v_input_2|true|Show SSL1|
|v_input_3|false|Show ATR bands|
|v_input_4|14|ATR Period|
|v_input_5|true|ATR Multi|
|v_input_6|0|ATR Smoothing: WMA|SMA|EMA|RMA|
|v_input_7|0|SSL1 / Baseline Type: HMA|EMA|DEMA|TEMA|LSMA|WMA|MF|VAMA|TMA|SMA|JMA|Kijun v2|EDSMA|McGinley|
|v_input_8|60|SSL1 / Baseline Length|
|v_input_9|0|SSL2 / Continuation Type: JMA|EMA|DEMA|TEMA|WMA|MF|VAMA|TMA|HMA|SMA|McGinley|
|v_input_10|5|SSL 2 Length|
|v_input_11|0|EXIT Type: HMA|TEMA|LSMA|VAMA|TMA|DEMA|JMA|Kijun v2|McGinley|MF|
|v_input_12|15|EXIT Length|
|v_input_13_close|0|Source: close|high|low|open|hl2|hlc3|hlcc4|ohlc4|
|v_input_14|true|Kijun MOD Divider|
|v_input_15|3|* Jurik (JMA) Only - Phase|
|v_input_16|true|* Jurik (JMA) Only - Power|
|v_input_17|10|* Volatility Adjusted (VAMA) Only - Volatility lookback length|
|v_input_18|0.8|Modular Filter, General Filter Only - Beta|
|v_input_19|false|Modular Filter Only - Feedback|
|v_input_20|0.5|Modular Filter Only - Feedback Weighting|
|v_input_21|20|EDSMA - Super Smoother Filter Length|
|v_input_22|0|EDSMA - Super Smoother Filter Poles: 2|3|
|v_input_23|true|useTrueRange|
|v_input_24|0.2|Base Channel Multiplier|
|v_input_25|true|Color Bars|
|v_input_26|0.9|Continuation ATR Criteria|
|v_input_39|14|(?Strategy Back Test Settings)ATR Length|
|v_input_40|timestamp(01 Aug 2021 00:00 +0100)|(?Date Range)From|
|v_input_41|timestamp(01 Sep 2021 00:00 +0100)|To|
|v_input_42|false|(?Entry Settings)SSL Flip as Filter|
|v_input_43|false|QQE MOD as Filter (Please add QQE MOD indicator to your chart separately)|
|v_input_44|0.1|DCA1 ATR Multiplier|
|v_input_45|20|DCA1 Exit Percentage|
|v_input_46|0.3|DCA2 ATR Multiplier|
|v_input_47|40|DCA2 Exit Percentage|
|v_input_48|0.7|DCA3 ATR Multiplier|
|v_input_49|40|DCA3 Exit Percentage|
|v_input_50|1.8|(?Exit Settings)SL ATR Multiplier|


> Source (PineScript)

``` javascript
/*backtest
start: 2023-11-28 00:00:00
end: 2023-12-05 00:00:00
period: 1m
basePeriod: 1m
exchanges: [{"eid":"Futures_Binance","currency":"BTC_USDT"}]
args: [["TradeAmount",2,358374]]
*/

//@version=4

// Strategy based on the SSL Hybrid indicator by Mihkel00
// Designed for the purpose of back testing
// Strategy:
//  - Enters both long and short trades based on SSL1 crossing the baseline
//  - Stop Loss calculated based on ATR multiplier
//  - Take Profit calculated based on 2 ATR multipliers and exits percentage of position on TP1 and TP2
//
// Credits:
// SSL Hybrid Mihkel00 https://www.tradingview.com/u/Mihkel00/

// -------------------------------- SSL HYBRID ---------------------------------
strategy("SSL Exit Arrow Strategy", overlay=true)
show_Baseline = input(title="Show Baseline", type=input.bool, defval=true, group="SSL Hybrid Indicator Settings")
show_SSL1 = input(title="Show SSL1", type=input.bool, defval=true, group="SSL Hybrid Indicator Settings")
show_atr = input(title="Show ATR bands", type=input.bool, defval=false, group="SSL Hybrid Indicator Settings")
//ATR
atrlen = input(14, "ATR Period", group="SSL Hybrid Indicator Settings")
mult = input(1, "ATR Multi", step=0.1, group="SSL Hybrid Indicator Settings")
smoothing = input(title="ATR Smoothing", defval="WMA", options=["RMA", "SMA", "EMA", "WMA"], group="SSL Hybrid Indicator Settings")

ma_function(source, atrlen) => 
    if smoothing == "RMA"
        rma(source, atrlen)
    else
        if smoothing == "SMA"
            sma(source, atrlen)
        else
            if smoothing == "EMA"
                ema(source, atrlen)
            else
                wma(source, atrlen)
atr_slen = ma_function(tr(true), atrlen)
////ATR Up/Low Bands
upper_band = atr_slen * mult + close
lower_band = close - atr_slen * mult

////BASELINE / SSL1 / SSL2 / EXIT MOVING AVERAGE VALUES
maType = input(title="SSL1 / Baseline Type", type=input.string, defval="HMA", options=["SMA","EMA","DEMA","TEMA","LSMA","WMA","MF","VAMA","TMA","HMA", "JMA", "Kijun v2", "EDSMA","McGinley"], group="SSL Hybrid Indicator Settings")
len = input(title="SSL1 / Baseline Length", defval=60, group="SSL Hybrid Indicator Settings")

SSL2Type = input(title="SSL2 / Continuation Type", type=input.string, defval="JMA", options=["SMA","EMA","DEMA","TEMA","WMA","MF","VAMA","TMA","HMA", "JMA","McGinley"], group="SSL Hybrid Indicator Settings")
len2 = input(title="SSL 2 Length", defval=5, group="SSL Hybrid Indicator Settings")
//
SSL3Type = input(title="EXIT Type", type=input.string, defval="HMA", options=["DEMA","TEMA","LSMA","VAMA","TMA","HMA","JMA", "Kijun v2", "McGinley", "MF"], group="SSL Hybrid Indicator Settings")
len3 = input(title="EXIT Length", defval=15, group="SSL Hybrid Indicator Settings")
src = input(title="Source", type=input.source, defval=close, group="SSL Hybrid Indicator Settings")

//
tema(src, len) =>
    ema1 = ema(src, len)
    ema2 = ema(ema1, len)
    ema3 = ema(ema2, len)
    (3 * ema1) - (3 * ema2) + ema3
kidiv = input(defval=1,maxval=4,  title="Kijun MOD Divider", group="SSL Hybrid Indicator Settings")

jurik_phase = input(title="* Jurik (JMA) Only - Phase", type=input.integer, defval=3, group="SSL Hybrid Indicator Settings")
jurik_power = input(title="* Jurik (JMA) Only - Power", type=input.integer, defval=1, group="SSL Hybrid Indicator Settings")
volatility_lookback = input(10, title="* Volatility Adjusted (VAMA) Only - Volatility lookback length", group="SSL Hybrid Indicator Settings")
//MF
beta = input(0.8,minval=0,maxval=1,step=0.1,  title="Modular Filter, General Filter Only - Beta", group="SSL Hybrid Indicator Settings")
feedback = input(false, title="Modular Filter Only - Feedback", group="SSL Hybrid Indicator Settings")
z = input(0.5,title="Modular Filter Only - Feedback Weighting",step=0.1, minval=0, maxval=1, group="SSL Hybrid Indicator Settings")
//EDSMA
ssfLength = input(title="EDSMA - Super Smoother Filter Length", type=input.integer, minval=1, defval=20, group="SSL Hybrid Indicator Settings")
ssfPoles = input(title="EDSMA - Super Smoother Filter Poles", type=input.integer, defval=2, options=[2, 3], group="SSL Hybrid Indicator Settings")

//----

//EDSMA
get2PoleSSF(src, length) =>
    PI = 2 * asin(1)
    arg = sqrt(2) * PI / length
    a1 = exp(-arg)
    b1 = 2 * a1 * cos(arg)
    c2 = b1
    c3 = -pow(a1, 2)
    c1 = 1 - c2 - c3
    
    ssf = 0.0
    ssf := c1 * src + c2 * nz(ssf[1]) + c3 * nz(ssf[2])

get3PoleSSF(src, length) =>
    PI = 2 * asin(1)

    arg = PI / length
    a1 = exp(-arg)
    b1 = 2 * a1 * cos(1.738 * arg)
    c1 = pow(a1, 2)

    coef2 = b1 + c1
    coef3 = -(c1 + b1 * c1)
    coef4 = pow(c1, 2)
    coef1 = 1 - coef2 - coef3 - coef4

    ssf = 0.0
    ssf := coef1 * src + coef2 * nz(ssf[1]) + coef3 * nz(ssf[2]) + coef4 * nz(ssf[3])

ma(type, src, len) =>
    float result = 0
    if type=="TMA"
        result := sma(sma(src, ceil(len / 2)), floor(len / 2) + 1)
    if type=="MF"
        ts=0.,b=0.,c=0.,os=0.
        //----
        alpha = 2/(len+1)
        a = feedback ? z*src + (1-z)*nz(ts[1],src) : src
        //----
        b := a > alpha*a+(1-alpha)*nz(b[1],a) ? a : alpha*a+(1-alpha)*nz(b[1],a)
        c := a < alpha*a+(1-alpha)*nz(c[1],a) ? a : alpha*a+(1-alpha)*nz(c[1],a)
        os := a == b ? 1 : a == c ? 0 : os[1]
        //----
        upper = beta*b+(1-beta)*c
        lower = beta*c+(1-beta)*b 
        ts := os*upper+(1-os)*lower
        result := ts
    if type=="LSMA"
        result := linreg(src, len, 0)
    if type=="SMA" // Simple
        result := sma(src, len)
    if type=="EMA" // Exponential
        result := ema(src, len)
    if type=="DEMA" // Double Exponential
        e = ema(src, len)
        result := 2 * e - ema(e, len)
    if type=="TEMA" // Triple Exponential
        e = ema(src, len)
        result := 3 * (e - ema(e, len)) + ema(ema(e, len), len)
    if type=="WMA" // Weighted
        result := wma(src, len)
    if type=="VAMA" // Volatility Adjusted
        /// Copyright © 2019 to present, Joris Duyck (JD)
        mid=ema(src,len)
        dev=src-mid
        vol_up=highest(dev,volatility_lookback)
        vol_down=lowest(dev,volatility_lookback)
        result := mid+avg(vol_up,vol_down)
    if type=="HMA" // Hull
        result := wma(2 * wma(src, len / 2) - wma(src, len), round(sqrt(len)))
    if type=="JMA" // Jurik
        /// Copyright © 2018 Alex Orekhov (everget)
        /// Copyright © 2017 Jurik Research and Consulting.
        phaseRatio = jurik_phase < -100 ? 0.5 : jurik_phase > 100 ? 2.5 : jurik_phase / 100 + 1.5
        beta = 0.45 * (len - 1) / (0.45 * (len - 1) + 2)
        alpha = pow(beta, jurik_power)
        jma = 0.0
        e0 = 0.0
        e0 := (1 - alpha) * src + alpha * nz(e0[1])
        e1 = 0.0
        e1 := (src - e0) * (1 - beta) + beta * nz(e1[1])
        e2 = 0.0
        e2 := (e0 + phaseRatio * e1 - nz(jma[1])) * pow(1 - alpha, 2) + pow(alpha, 2) * nz(e2[1])
        jma := e2 + nz(jma[1])
        result := jma
    if type=="Kijun v2"
        kijun = avg(lowest(len), highest(len))//, (open + close)/2)
        conversionLine = avg(lowest(len/kidiv), highest(len/kidiv))
        delta = (kijun + conversionLine)/2
        result :=delta
    if type=="McGinley"
        mg = 0.0
        ema = ema(src, len)
        mg := na(mg[1]) ? ema : mg[1] + (src - mg[1]) / (len * pow(src/mg[1], 4))
        result :=mg
    if type=="EDSMA"
    
        zeros = src - nz(src[2])
        avgZeros = (zeros + zeros[1]) / 2
        
        // Ehlers Super Smoother Filter 
        ssf = ssfPoles == 2
             ? get2PoleSSF(avgZeros, ssfLength)
             : get3PoleSSF(avgZeros, ssfLength)
        
        // Rescale filter in terms of Standard Deviations
        stdev = stdev(ssf, len)
        scaledFilter = stdev != 0
             ? ssf / stdev
             : 0
        
        alpha = 5 * abs(scaledFilter) / len
        
        edsma = 0.0
        edsma := alpha * src + (1 - alpha) * nz(edsma[1])
        result :=  edsma
    result
    
///SSL 1 and SSL2
emaHigh = ma(maType, high, len)
emaLow = ma(maType, low, len)

maHigh = ma(SSL2Type, high, len2)
maLow = ma(SSL2Type, low, len2)

///EXIT
ExitHigh = ma(SSL3Type, high, len3)
ExitLow = ma(SSL3Type, low, len3)

///Keltner Baseline Channel
BBMC = ma(maType, close, len)
useTrueRange = input(true, group="SSL Hybrid Indicator Settings")
multy = input(0.2, step=0.05, title="Base Channel Multiplier", group="SSL Hybrid Indicator Settings")
Keltma = ma(maType, src, len)
range = useTrueRange ? tr : high - low
rangema = ema(range, len)
upperk =Keltma + rangema * multy
lowerk = Keltma - rangema * multy

//Baseline Violation Candle
open_pos =  open*1
close_pos = close*1
difference = abs(close_pos-open_pos)
atr_violation = difference > atr_slen
InRange = upper_band > BBMC and lower_band < BBMC
candlesize_violation = atr_violation and InRange
plotshape(candlesize_violation, color=color.new(color.white, transp=0), size=size.tiny,style=shape.diamond, location=location.top, title="Candle Size > 1xATR")


//SSL1 VALUES
Hlv = int(na)
Hlv := close > emaHigh ? 1 : close < emaLow ? -1 : Hlv[1]
sslDown = Hlv < 0 ? emaHigh : emaLow

//SSL2 VALUES
Hlv2 = int(na)
Hlv2 := close > maHigh ? 1 : close < maLow ? -1 : Hlv2[1]
sslDown2 = Hlv2 < 0 ? maHigh : maLow

//EXIT VALUES
Hlv3 = int(na)
Hlv3 := close > ExitHigh ? 1 : close < ExitLow ? -1 : Hlv3[1]
sslExit = Hlv3 < 0 ? ExitHigh : ExitLow
base_cross_Long = crossover(close, sslExit)
base_cross_Short = crossover(sslExit, close)
codiff = base_cross_Long ? 1 : base_cross_Short ? -1 : na 

//COLORS
show_color_bar = input(title="Color Bars", type=input.bool, defval=true, group="SSL Hybrid Indicator Settings")
color_bar = close > upperk ? #00c3ff : close < lowerk ? #ff0062 : color.gray
color_ssl1 = close > sslDown ? #00c3ff : close < sslDown ? #ff0062 : na

//PLOTS
plotarrow(codiff, colorup=color.rgb(0, 195, 255, transp=0), colordown=color.rgb(255, 0, 98, transp=0),title="Exit Arrows", maxheight=20, offset=0)
p1 = plot(show_Baseline ? BBMC : na, color=color.new(color_bar, transp=0), linewidth=4, title='MA Baseline')
DownPlot = plot( show_SSL1 ? sslDown : na, title="SSL1", linewidth=3, color=color.new(color_ssl1, transp=10))
barcolor(show_color_bar ? color_bar : na)
up_channel = plot(show_Baseline ? upperk : na, color=color_bar, title="Baseline Upper Channel")
low_channel = plot(show_Baseline ? lowerk : na, color=color_bar, title="Basiline Lower Channel")
fill(up_channel, low_channel, color=color.new(color_bar, transp=90))

////SSL2 Continiuation from ATR
atr_crit = input(0.9, step=0.1, title="Continuation ATR Criteria", group="SSL Hybrid Indicator Settings")
upper_half = atr_slen * atr_crit + close
lower_half = close - atr_slen * atr_crit
buy_inatr =  lower_half < sslDown2
sell_inatr = upper_half > sslDown2
sell_cont = close < BBMC and close < sslDown2
buy_cont = close > BBMC and close > sslDown2
sell_atr = sell_inatr and sell_cont
buy_atr = buy_inatr and buy_cont
atr_fill = buy_atr ? color.green : sell_atr ? color.purple : color.white
LongPlot = plot(sslDown2, title="SSL2", linewidth=2, color=color.new(atr_fill, transp=0), style=plot.style_circles, display=display.none)
u = plot(show_atr ? upper_band : na, "+ATR", color=color.new(color.white, transp=80), display=display.none)
l = plot(show_atr ? lower_band : na, "-ATR", color=color.new(color.white, transp=80), display=display.none)

// ---------------------------- QQE MOD INDICATOR ------------------------------
RSI_Period = input(6, title='RSI Length')
SF = input(5, title='RSI Smoothing')
QQE = input(3, title='Fast QQE Factor')
ThreshHold = input(3, title="Thresh-hold")

rsi_src = input(close, title="RSI Source")

Wilders_Period = RSI_Period * 2 - 1


Rsi = rsi(rsi_src, RSI_Period)
RsiMa = ema(Rsi, SF)
AtrRsi = abs(RsiMa[1] - RsiMa)
MaAtrRsi = ema(AtrRsi, Wilders_Period)
dar = ema(MaAtrRsi, Wilders_Period) * QQE

longband = 0.0
shortband = 0.0
trend = 0

DeltaFastAtrRsi = dar
RSIndex = RsiMa
newshortband = RSIndex + DeltaFastAtrRsi
newlongband = RSIndex - DeltaFastAtrRsi
longband := RSIndex[1] > longband[1] and RSIndex > longband[1] ? 
   max(longband[1], newlongband) : newlongband
shortband := RSIndex[1] < shortband[1] and RSIndex < shortband[1] ? 
   min(shortband[1], newshortband) : newshortband
cross_1 = cross(longband[1], RSIndex)
trend := cross(RSIndex, shortband[1]) ? 1 : cross_1 ? -1 : nz(trend[1], 1)
FastAtrRsiTL = trend == 1 ? longband : shortband
////////////////////


length = input(50, minval=1, title="Bollinger Length")
bb_mult = input(0.35, minval=0.001, maxval=5, step=0.1, title="BB Multiplier")
basis = sma(FastAtrRsiTL - 50, length)
dev = bb_mult * stdev(FastAtrRsiTL - 50, length)
upper = basis + dev
lower = basis - dev
rsi_ma_color_bar = RsiMa - 50 > upper ? #00c3ff : RsiMa - 50 < lower ? #ff0062 : color.gray


// Zero cross
QQEzlong = 0
QQEzlong := nz(QQEzlong[1])
QQEzshort = 0
QQEzshort := nz(QQEzshort[1])
QQEzlong := RSIndex >= 50 ? QQEzlong + 1 : 0
QQEzshort := RSIndex < 50 ? QQEzshort + 1 : 0

////////////////////////////////////////////////////////////////

RSI_Period2 = input(6, title='RSI Length')
SF2 = input(5, title='RSI Smoothing')
QQE2 = input(1.61, title='Fast QQE2 Factor')
ThreshHold2 = input(3, title="Thresh-hold")

src2 = input(close, title="RSI Source")

Wilders_Period2 = RSI_Period2 * 2 - 1


Rsi2 = rsi(src2, RSI_Period2)
RsiMa2 = ema(Rsi2, SF2)
AtrRsi2 = abs(RsiMa2[1] - RsiMa2)
MaAtrRsi2 = ema(AtrRsi2, Wilders_Period2)
dar2 = ema(MaAtrRsi2, Wilders_Period2) * QQE2
longband2 = 0.0
shortband2 = 0.0
trend2 = 0

DeltaFastAtrRsi2 = dar2
RSIndex2 = RsiMa2
newshortband2 = RSIndex2 + DeltaFastAtrRsi2
newlongband2 = RSIndex2 - DeltaFastAtrRsi2
longband2 := RSIndex2[1] > longband2[1] and RSIndex2 > longband2[1] ? 
   max(longband2[1], newlongband2) : newlongband2
shortband2 := RSIndex2[1] < shortband2[1] and RSIndex2 < shortband2[1] ? 
   min(shortband2[1], newshortband2) : newshortband2
cross_2 = cross(longband2[1], RSIndex2)
trend2 := cross(RSIndex2, shortband2[1]) ? 1 : cross_2 ? -1 : nz(trend2[1], 1)
FastAtrRsi2TL = trend2 == 1 ? longband2 : shortband2

// Zero cross
QQE2zlong = 0
QQE2zlong := nz(QQE2zlong[1])
QQE2zshort = 0
QQE2zshort := nz(QQE2zshort[1])
QQE2zlong := RSIndex2 >= 50 ? QQE2zlong + 1 : 0
QQE2zshort := RSIndex2 < 50 ? QQE2zshort + 1 : 0

hcolor2 = RsiMa2 - 50 > ThreshHold2 ? color.silver :
   RsiMa2 - 50 < 0 - ThreshHold2 ? color.silver : na

Greenbar1 = RsiMa2 - 50 > ThreshHold2
Greenbar2 = RsiMa - 50 > upper

Redbar1 = RsiMa2 - 50 < 0 - ThreshHold2
Redbar2 = RsiMa - 50 < lower

qqe_line = FastAtrRsi2TL - 50
qqe_blue_bar = Greenbar1 and Greenbar2 == 1
qqe_red_bar = Redbar1 and Redbar2 == 1

// ----------------------------------STRATEGY ----------------------------------

atr_length = input(title="ATR Length", type=input.integer, defval=14, inline="1", group="Strategy Back Test Settings")
atr = atr(atr_length)

// Back test time range
from_date = input(title="From", type=input.time, defval=timestamp("01 Aug 2021 00:00 +0100"), inline="1", group="Date Range")
to_date = input(title="To", type=input.time, defval=timestamp("01 Sep 2021 00:00 +0100"), inline="1", group="Date Range")
in_date = true

// Strategy entry and exit settings

// Should use SSL as a filter for position side
use_ssl_filter = input(title="SSL Flip as Filter", type=input.bool, defval=false, inline="1", group="Entry Settings")
// Should use SSL as a filter for position side
use_qqe_filter = input(title="QQE MOD as Filter (Please add QQE MOD indicator to your chart separately)", type=input.bool, defval=false, inline="2", group="Entry Settings")

// DCA Settings
dca1_atr_multiplier = input(title="DCA1 ATR Multiplier", type=input.float, defval=0.1, step=0.1, inline="3", group="Entry Settings")
dca1_exit_percentage = input(title="DCA1 Exit Percentage", type=input.integer, defval=20, step=1, maxval=100, inline="3", group="Entry Settings")

dca2_atr_multiplier = input(title="DCA2 ATR Multiplier", type=input.float, defval=0.3, step=0.1, inline="4", group="Entry Settings")
dca2_exit_percentage = input(title="DCA2 Exit Percentage", type=input.integer, defval=40, step=1, maxval=100, inline="4", group="Entry Settings")

dca3_atr_multiplier = input(title="DCA3 ATR Multiplier", type=input.float, defval=0.7, step=0.1, inline="5", group="Entry Settings")
dca3_exit_percentage = input(title="DCA3 Exit Percentage", type=input.integer, defval=40, step=1, maxval=100, inline="5", group="Entry Settings")

// Stop-Loss Settings
sl_atr_multiplier = input(title="SL ATR Multiplier", type=input.float, defval=1.8, step=0.1, inline="2", group="Exit Settings")

var long_sl = float(na)
var long_dca1 = float(na)
var long_dca2 = float(na)
var long_dca3 = float(na)

var short_sl = float(na)
var short_dca1 = float(na)
var short_dca2 = float(na)
var short_dca3 = float(na)

is_open_long = strategy.position_size > 0
is_open_short = strategy.position_size < 0

var in_ssl_long = false
var in_ssl_short = false

var ssl_long_entry = false
var ssl_short_entry = false
var ssl_long_exit = false
var ssl_short_exit = false

var did_prev_bar_ssl_flip = false

ssl_long = use_ssl_filter ? close > sslDown : true
ssl_short = use_ssl_filter ? close < sslDown : true
qqe_long = use_qqe_filter ? (qqe_blue_bar and qqe_line > 0) : true
qqe_short = use_qqe_filter ? (qqe_red_bar and qqe_line < 0) : true

ssl_long_entry := ssl_long and qqe_long and codiff == 1
ssl_short_entry := ssl_short and qqe_short and codiff == -1
ssl_long_exit := codiff == -1
ssl_short_exit := codiff == 1

remaining_percent = 100
var total_tokens = strategy.equity * 0.10 / close

dca1_percent = dca1_exit_percentage <= remaining_percent ? dca1_exit_percentage : remaining_percent
remaining_percent -= dca1_percent
entry_1 = total_tokens * (dca1_percent / 100)

dca2_percent = dca2_exit_percentage <= remaining_percent ? dca2_exit_percentage : remaining_percent
remaining_percent -= dca2_percent
entry_2 = total_tokens * (dca2_percent / 100)

dca3_percent = dca3_exit_percentage <= remaining_percent ? dca3_exit_percentage : remaining_percent
remaining_percent -= dca3_percent
entry_3 = total_tokens * (dca3_percent / 100)
    
if did_prev_bar_ssl_flip
    did_prev_bar_ssl_flip := false
    position_value = abs(strategy.position_size * close)
    if in_ssl_long
        label.new(x=bar_index, y=close, xloc=xloc.bar_index, yloc=yloc.abovebar, text=tostring(position_value), style=label.style_label_down, size=size.tiny)
    else
        label.new(x=bar_index, y=close, xloc=xloc.bar_index, yloc=yloc.belowbar, text=tostring(position_value), style=label.style_label_up, size=size.tiny)

if ssl_long_exit
    strategy.cancel("LongEntry1")
    strategy.cancel("LongEntry2")
    strategy.cancel("LongEntry3")
    strategy.close(id="LongEntry1", comment="Close Long1")
    strategy.close(id="LongEntry2", comment="Close Long2")
    strategy.close(id="LongEntry3", comment="Close Long3")
    in_ssl_long := false
    in_ssl_short := false
    
if ssl_short_exit
    strategy.cancel("ShortEntry1")
    strategy.cancel("ShortEntry2")
    strategy.cancel("ShortEntry3")
    strategy.close(id="ShortEntry1", comment="Close Short1")
    strategy.close(id="ShortEntry2", comment="Close Short2")
    strategy.close(id="ShortEntry3", comment="Close Short3")
    in_ssl_long := false
    in_ssl_short := false

if ssl_long_entry and in_date and not in_ssl_long
    strategy.cancel("LongEntry1")
    strategy.cancel("LongEntry2")
    strategy.cancel("LongEntry3")
    strategy.cancel("ShortEntry1")
    strategy.cancel("ShortEntry2")
    strategy.cancel("ShortEntry3")
    
    if in_ssl_short
        strategy.close(id="ShortEntry1", comment="Close Short1")
        strategy.close(id="ShortEntry2", comment="Close Short2")
        strategy.close(id="ShortEntry3", comment="Close Short3")
        
    in_ssl_long := true
    in_ssl_short := false
    did_prev_bar_ssl_flip := true
    long_sl := close - (atr * sl_atr_multiplier)
    long_dca1 := close - (atr * dca1_atr_multiplier)
    long_dca2 := close - (atr * dca2_atr_multiplier)
    long_dca3 := close - (atr * dca3_atr_multiplier)

    strategy.entry("LongEntry1", strategy.long, limit=long_dca1)
    strategy.entry("LongEntry2", strategy.long, limit=long_dca2)
    strategy.entry("LongEntry3", strategy.long, limit=long_dca3)

    strategy.exit("LongExit1", "LongEntry1", stop=long_sl)
    strategy.exit("LongExit2", "LongEntry2", stop=long_sl)
    strategy.exit("LongExit3", "LongEntry3", stop=long_sl)

if ssl_short_entry and in_date and not in_ssl_short
    
    strategy.cancel("LongEntry1")
    strategy.cancel("LongEntry2")
    strategy.cancel("LongEntry3")
    strategy.cancel("ShortEntry1")
    strategy.cancel("ShortEntry2")
    strategy.cancel("ShortEntry3")
    
    if in_ssl_long
        strategy.close(id="LongEntry1", comment="Close Long1")
        strategy.close(id="LongEntry2", comment="Close Long2")
        strategy.close(id="LongEntry3", comment="Close Long3")
        
    in_ssl_short := true
    in_ssl_long := false
    did_prev_bar_ssl_flip := true
    short_sl := close + (atr * sl_atr_multiplier)
    short_dca1 := close + (atr * dca1_atr_multiplier)
    short_dca2 := close + (atr * dca2_atr_multiplier)
    short_dca3 := close + (atr * dca3_atr_multiplier)
    
    strategy.entry("ShortEntry1", strategy.short, limit=short_dca1)
    strategy.entry("ShortEntry2", strategy.short, limit=short_dca2)
    strategy.entry("ShortEntry3", strategy.short, limit=short_dca3)
    
    strategy.exit("ShortExit1", "ShortEntry1", stop=short_sl)
    strategy.exit("ShortExit2", "ShortEntry2", stop=short_sl)
    strategy.exit("ShortExit3", "ShortEntry3", stop=short_sl)

```

> Detail

https://www.fmz.com/strategy/434461

> Last Modified

2023-12-06 15:54:12
