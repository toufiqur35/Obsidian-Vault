### Home Controller

```php
class HomeController extends Controller
{
    function HomePage1()
    {
        $num1=70;
        $num2=20;
        $sum=$num1+$num2;
        return view('home1',['marks'=>$sum]);
    }
    
    function HomePage2()
    {
        $num1=70;
        $num2=20;
        $sum=$num1+$num2;
        return view('home2',['marks'=>$sum]);
    }
}
```
### If Else

```php
<h1>Sum is={{$marks}}</h1>

@if($marks>=80 && $marks<100)
    <h1>A+</h1>
@elseif($marks>=70 && $marks<80)
    <h1>A</h1>
@elseif($marks>=60 && $marks<70)
    <h1>A-</h1>
@elseif($marks>=50 && $marks<60)
    <h1>B</h1>
@else
    <h1>F</h1>
    
@endif
```

### Assets binding

```php
<img src="{{asset('https://captainbinary.com/images/hero-img.svg')}}"/>
```

### Witch Case

```php
@switch($marks)
    @case(100)
        <h1>A++++</h1>
        @break
    @case(70)
        <h1>A----</h1>
        @break
    @default
        <h1>Don`t Know</h1>
@endswitch
```

### Loop

```php
@for($i=0; $i<100;$i++)

    The Loop Value is={{$i}} <br/>

@endfor
```

### Master Layout

layout\\`app.blade.php`
```php
<html>
<head>

<title>Home Page</title>

<meta name="viewport" content="width=device-width, initial-scale=1"/>
<meta name="description" content="Laravel Point is your one-stop destination for mastering the Laravel framework. Whether you're a beginner looking to start your journey in web development or an experienced developer aiming to enhance your Laravel skills, this dedicated learning platform has you covered. With a wide range of tutorials, articles, video lessons, and interactive coding challenges, Laravel Point provides a comprehensive and structured learning experience.">
<meta name="keywords" content="Laravel  tutorial bangla, Expert Web Developer in Bangladesh, Expert Mobile App Developer in Bangladesh, Android App Developer in Bangladesh">
<meta name="author" content="Laravel Point">
<meta property="og:site_name" content="Laravel Point">
<meta property="og:url" content="https://Laravelpoint.com" />
<meta property="og:title" content="Learn Confidently with Laravel Point" />
<meta property="og:description" content="Laravel Point is your one-stop destination for mastering the Laravel framework. Whether you're a beginner looking to start your journey in web development or an experienced developer aiming to enhance your Laravel skills, this dedicated learning platform has you covered. With a wide range of tutorials, articles, video lessons, and interactive coding challenges, Laravel Point provides a comprehensive and structured learning experience." />
<meta property="og:image" content="https://laravelpoint.com/indexseo.jpg"/>

<link rel="stylesheet" href="{{asset('<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">')}}">
<link rel="stylesheet" href="{{asset('css/style.css')}}">

</head>
<body>

@yield('content')

</body>
</html>
```

### Use

`home.blade.php`
```php

@extends('layout.app')

@section('content')
<h1>HOME PAGE 1</h1>
@include('components.NavBar')
@include('components.Hero')
@include('components.loop')
@include('components.List')
@include('components.Footer')

@endsection
```


### Master Layout Another Way

layout\\`app.blade.php`
```php
<html>
<head>

<title>Home Page</title>

<meta name="viewport" content="width=device-width, initial-scale=1"/>
<meta name="description" content="Laravel Point is your one-stop destination for mastering the Laravel framework. Whether you're a beginner looking to start your journey in web development or an experienced developer aiming to enhance your Laravel skills, this dedicated learning platform has you covered. With a wide range of tutorials, articles, video lessons, and interactive coding challenges, Laravel Point provides a comprehensive and structured learning experience.">
<meta name="keywords" content="Laravel  tutorial bangla, Expert Web Developer in Bangladesh, Expert Mobile App Developer in Bangladesh, Android App Developer in Bangladesh">
<meta name="author" content="Laravel Point">
<meta property="og:site_name" content="Laravel Point">
<meta property="og:url" content="https://Laravelpoint.com" />
<meta property="og:title" content="Learn Confidently with Laravel Point" />
<meta property="og:description" content="Laravel Point is your one-stop destination for mastering the Laravel framework. Whether you're a beginner looking to start your journey in web development or an experienced developer aiming to enhance your Laravel skills, this dedicated learning platform has you covered. With a wide range of tutorials, articles, video lessons, and interactive coding challenges, Laravel Point provides a comprehensive and structured learning experience." />
<meta property="og:image" content="https://laravelpoint.com/indexseo.jpg"/>

<link rel="stylesheet" href="{{asset('<link
href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">')}}">
<link rel="stylesheet" href="{{asset('css/style.css')}}">

</head>
<body>
@include('components.NavBar')

@yield('content')

@include('components.Footer')

</body>
</html>
```

### Use

`home.blade.php`
```php

@extends('layout.app')

@section('content')
<h1>HOME PAGE 1</h1>
@include('components.Hero')
@include('components.loop')
@include('components.List')

@endsection
```