# Api Para Condomínio 
- Biblioteca PHP para validacao da Api usando **Laravel**_

<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://travis-ci.org/laravel/framework"><img src="https://travis-ci.org/laravel/framework.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

-----------------------------------------------------------------------------------------------------------------------

## Como usar
Para Facilitar a utilizacão, use a ferramenta Postman para fazer e enviar as requisicões

- Criar usuários 
Route::post('/auth/register', [AuthController::class, 'register']);

```php
    $validator = Validator::make($request->all(), [
        'name' => 'required',
        'email' => 'required|email|unique:users,email',
        'cpf' => 'required|digits:11|unique:users,cpf',
        'password' => 'required',
        'password_confirm' => 'required|same:password',
    ]);
```

- Login 
Route::post('/auth/login', [AuthController::class, 'login']);
```php
        $cpf = $request->input('cpf');
        $password = $request->input('password');

```

Route::post('/auth/validate', [AuthController::class, 'validateToken']);
    ```Route::post('/auth/logout', [AuthController::class, 'logout']);``` - Logout

    ```Route::put('/user', [UserController::class, 'update']);```  - Editar informacões

    //Moral de Avisos
    ```Route::get('/walls', [WallController::class, 'getAll']);``` - Pegar todos os avisos

    ```Route::post('/wall/{id}/like', [WallController::class, 'like']);``` - Dar like nos avisos

    //Documentos
    ```Route::get('/docs', [DocController::class, 'getAll']);``` - Pegar todos os documentos

    //Livros de ocorrências
    ```Route::get('/warnings', [WarningController::class, 'getMyWarnings']);``` - Pegar Todas as ocorrências

    ```Route::post('/warning', [WarningController::class, 'setWarning']);``` - Adicionar ocorrência

    ```Route::post('/warning/file', [WarningController::class, 'addWarningFile']);``` - Adicionar Foto e anexar a ocorrência

    //Boletos
    ```Route::get('/billets', [BilletController::class, 'getAll']);``` Pegar todos os boletos 

    //Achados e Perdidos 
    ```Route::get('/foundandlost', [FoundAndLostController::class, 'getAll']);``` - Ver todos os achados e perdidos

    ```Route::post('/foundandlost', [FoundAndLostController::class, 'insert']);``` - Inserir novo objeto no achados e perdidos

    ```Route::put('/foundandlost/{id}', [FoundAndLostController::class, 'update']);``` - Atualizar informacões no achados e perdidos. exemplo - Objeto devolvido 

    //Unidade
    ```Route::get('/unit/{id}', [UnitController::class, 'getInfo']);``` Informacões de cada apartamento por Id

    ```Route::post('/unit/{id}/addperson', [UnitController::class, 'addPerson']);``` - Adicionar nova pessoa

    ```Route::post('/unit/{id}/addvehicle', [UnitController::class, 'addVehicle']);``` - Adicionar novo veículo

    ```Route::post('/unit/{id}/addpet', [UnitController::class, 'addPet']);``` - Adicionar novo Pet 

    ```Route::post('/unit/{id}/removeperson', [UnitController::class, 'removePerson']);``` - Remover Pessoa 

    ```Route::post('/unit/{id}/removevehicle', [UnitController::class, 'removeVehicle']);``` - Remover Veículo

    ```Route::post('/unit/{id}/removepet', [UnitController::class, 'removePet']);``` - Remover Pet
     
    //Reservas 
   ```Route::get('/reservations', [ReservationController::class, 'getReservations']);``` - Ver todas reservas das áreas de lazer

    ```Route::post('/reservation/{id}', [ReservationController::class, 'setReservation']);``` - Fazer uma reserva 

    ```Route::get('/reservation/{id}/disableddates', [ReservationController::class, 'getDisabledDates']);``` - Dias desativados. exemplo: horario ou dia de manutencão ou limpeza da área.

    ```Route::get('/reservation/{id}/times', [ReservationController::class, 'getTimes']);``` - Horarios de reservas

    ```Route::get('/myreservations', [ReservationController::class, 'getMyReservations']);``` - Minhas reservas

    ```Route::delete('/myreservation/{id}', [ReservationController::class, 'deleteMyReservation']); - Excluir reservas 



Fique a vontade para contribuir de qualquer forma.