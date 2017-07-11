# Currency
A simple and cross platform currency class library that follows the ISO 4217 standard.

Currency is a value type, i.e, a struct, with no public constructor, but simple, quick methods that return you the currency instance you want instead.

### Usage
First, you need to import the class:

``` c#
using AndreMarcondesTeixeira;
```

Then, you can get a currency instance by three ways:

1. Calling a factory property, where XXX is the three letters ISO code of the currency:

``` c#
var currency = Currency.XXX;
```

2. Using the method GetByLetterCode, where, again, XXX is the three letters ISO code of the currency:

``` c#
var currency = Currency.GetByLetterCode("XXX");
```

3. Using the method GetByNumericCode, where 999 is the three numbers ISO code of the currency:

``` c#
var currency = Currency.GetByNumericCode("999"); //(Note that the numeric code is a string)
```

The Currency class have four read only properties:

``` c#
public struct Currency : IEquatable<Currency>
{
    /// <summary>The 3 letters ISO code of the currency</summary>
    public string LetterCode { get; }

    /// <summary>The ISO minor units of the currency</summary>
    public byte MinorUnits { get; }

    /// <summary>The ISO name of the currency</summary>
    public string Name { get; }

    /// <summary>The numeric ISO code of the currency</summary>
    public string NumericCode { get; }
}
```

You can compare currencies using the operators == and !=
``` c#
var areCurrenciesEquivalent = (Currency.XXX == Currency.XXX); // returns true;
var areCurrenciesEquivalent = (Currency.XXX != Currency.XXX); // returns false;
```