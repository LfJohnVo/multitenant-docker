<h1 align="center;">Multitenant laravel practice</h1>

<p>You need to have docker running*</p>

<h3>Command list<h2>
<ol>
    <li>./vendor/bin/sail up -d</li>
    <li>nano ~/.bashrc</li>
    <li>write: alias sail='bash vendor/bin/sail'</li>
    <li>. ~/.bashrc</li>
    <li>sail down</li>
    <li>sail up -d</li>
    <li>sail php artisan migrate:fresh --seed</li>
    <li>sail php artisan tinker</li>
    <li>$tenant1 = App\Models\Tenant::create(['id' => 'foo']);</li>
    <li>$tenant1->domains()->create(['domain' => 'foo.localhost']);</li>
    <li>$tenant2 = App\Models\Tenant::create(['id' => 'bar']);</li>
    <li>$tenant2->domains()->create(['domain' => 'bar.localhost']);</li>
    <li>App\Models\Tenant::all()->runForEach(function () {
    App\Models\User::factory()->create();});</li>
    <li>Now you can enter on foo.localhost ;)</li>
</ol>
