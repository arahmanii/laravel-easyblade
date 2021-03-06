# laravel EasyBlade

You can create a simpler and readable view with EasyBlade

# Install

```
composer require aminireza-ir/laravel-easyblade
```

# Usage

Use EasyBlade is too much easy like its name.

Imagine you want to write a route URL in a href in Blade
You can write this code : 
```html
    <a href="{{ route('home') }}"></a>
```
But We create a simpler way with EasyBlade 
Just write :
```html
    <a href="@route('home')"></a>
```
and don't use any {{ }} in your blade or don't use any PHP Pure code

Blade template engine has created to not code PHP Pure , It has created to code easier
You can do it by EasyBlade :) !

## Current Directives :

- `@asset('foo')`
- `@url('foo')`
- `@route('foo')`
- `@isActive('routeName', 'active', 'deactive')`
- `@count(array|collection, number )`
- `@user(attr)`

## Features :
 - You can pass a route name or array of route names as first parameters to```@isActive``` directive , second parameter is a string which you want to echo in view and third parameter is a optional param and it will return a null string if nothing passed , It will be showed when current route is not equal to array or string which passed as first param
 - You can use `@count` directive instead of write lots of if to check count of collection or array is equal or greater than your number which passed to second param.
 
## Examples : 
- `@count`
```blade
    @count([1, 2, 3], 3)
        something
    @endcount
    // return `something` because count of array is equal 3
```

```blade
    @count([1, 2], 3)
        true
    @endcount
    // return null because count of array is smaler than 3
```

- `@isActive` Imagine current route is : `dashboard.home`
```blade
    @isActive('dashboard.home', 'active', 'deactive')
    // Return : active
```
```blade
    @isActive(['dashboard.home', 'dahboard.profile'], 'active', 'deactive')
    // Return : active
```
```blade
    @isActive('home', 'active', 'deactive')
    // Return : deactive
```

- `@asset` 
```blade
    @asset('img/header.png')
    
    // Return : http://127.0.0.1/img/header.png (Like asset() helper )
```
- `@route` 
```blade
    @route('dashboard')
    
    // Return : http://127.0.0.1/dashboard (Like route('routeName') helper )
```

- `@url` 
```blade
    @url('/home')
    
    // Return : http://127.0.0.1/home (Like url('address') helper )
```

- `@user` 
```blade
    @user('name')
    
   // It will run auth()->user()->name and return user's name
   // You don't need to check user is authenticated or not , it will check by itself

```