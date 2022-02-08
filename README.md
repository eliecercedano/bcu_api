# API en Laravel basada en el plugin desarrollado por <a href="https://www.biller.uy" target="_blank">Biller</a> 
Permite obtener la tasa de conversión de Pesos Uruguayos a Dólares del Banco Central del Uruguay.<br />

## Instalación
Luego de clonar este repositorio, debes ingresar en el directorio del proyecto y ejecutar:
```
$ composer install
```
```
$ php artisan key:generate
```

El endpoint a utilizar es api/rate

<br />
Mayor información acerca del plugin:
<p align="center">
    <a href="https://www.biller.uy" target="_blank"><img src="https://www.biller.uy/images/logo/logo_biller.svg" width="400" alt="Biller - facturación electrónica" />
    </a>
</p>

# Adaptador de WebServices del BCU para PHP

Herramienta para obtener la cotización oficial de distintas monedas extraídas del WebService del [Banco Central del Uruguay](http://www.bcu.gub.uy/).

Los WebServices utilizados son [awsbcucotizaciones](https://cotizaciones.bcu.gub.uy/wscotizaciones/servlet/awsbcucotizaciones?wsdl) y [awsultimocierre](https://cotizaciones.bcu.gub.uy/wscotizaciones/servlet/awsultimocierre?wsdl).

La documentación oficial de los WebServices [puede ser encontrada aquí](https://www.scribd.com/document/371380764/Especificacion-WS-Cotizaciones).

## Instalación

La mejor forma de utilizar este plugin es a través del plugin [composer](http://getcomposer.org/download/).
```
composer require biller/bcu
```

## Uso

Luego de su instalación, se utiliza el método `obtenerCotizacion` que devolverá la última cotización de cierre para el dolar interbancario billete.

También se puede obtener la fecha del último cierre a través del llamado al método `obtenerUltimoCierre`.

### Obtener cotización
```php
// Dólar interbancario para el último día de cierre
biller\bcu\Cotizaciones::obtenerCotizacion();
```
```php
// Dólar interbancario para el 01-ene-2018
biller\bcu\Cotizaciones::obtenerCotizacion('2018-01-01');
```
```php
// Dólar interbancario para el 01-ene-2018
biller\bcu\Cotizaciones::obtenerCotizacion('2018-01-01', 2225);
```
El tercer parámetro indica el Grupo de Monedas.<br />
Grupo 1: Mercado Internacional<br />
Grupo 2: Cotizaciones Locales<br />
Grupo 0: ambos grupos
```php
// Euro para ambos Grupos de Monedas para el 01-ene-2018
biller\bcu\Cotizaciones::obtenerCotizacion('2018-01-01', 1111, 0);
```

### Obtener último cierre
```php
biller\bcu\Cotizaciones::obtenerUltimoCierre();
```


<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Cubet Techno Labs](https://cubettech.com)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[Many](https://www.many.co.uk)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com)**
- **[Curotec](https://www.curotec.com/)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
