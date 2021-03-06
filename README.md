# Photosphere.DependencyInjection.xUnit
[xUnit](https://github.com/xunit/xunit) extension for support [Photosphere.DependencyInjection](https://github.com/sunloving/photosphere-di).

## Status
[![Windows build Status](https://ci.appveyor.com/api/projects/status/github/sunloving/photosphere-di-xunit?retina=true&svg=true)](https://ci.appveyor.com/project/sunloving/photosphere-di-xunit)
[![NuGet](https://img.shields.io/nuget/v/Photosphere.DependencyInjection.xUnit.svg)](https://www.nuget.org/packages/Photosphere.DependencyInjection.xUnit/)
[![license](https://img.shields.io/github/license/mashape/apistatus.svg?maxAge=2592000)](https://github.com/sunloving/photosphere-di-xunit/blob/master/LICENSE)


## Install
```
PM> Install-Package Photosphere.DependencyInjection.xUnit
```

## How to use
Just use `InjectDependency` instead `InlineData` into your theories.
``` C#
[Theory]
[InjectDependency(42, "foo")]
void Test(int someNumber, string someString, IFoo foo, IBar bar)
{
  Assert.Equal(42, someNumber);
  Assert.Equal("foo", someString);
  Assert.NotNull(foo);
  Assert.NotNull(bar);
}

```
