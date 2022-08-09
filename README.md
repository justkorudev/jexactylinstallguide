# Install Jexactyl Easily (Ipv4 only)

Step 1: Execute this at the console

```bash
sudo -s
```

Step 2: Execute this at the console

```bash
bash <(curl -s https://pterodactyl-installer.se)
```

Step 3: Follow the script install steps (Select **2** to install everything we need) (You can see [this tutorial](https://www.youtube.com/watch?v=E8UJhyUFoHM) to know exactly how to get started)

```bash
bash <(curl -s https://pterodactyl-installer.se)
```

Step 4: Execute this at the console

```bash
cp -R /var/www/pterodactyl /var/www/pterodactyl-backup
```

Step 5: Execute this at the console

```bash
mysqldump -u root -p panel > /var/www/pterodactyl-backup/panel.sql
```

Step 6: Execute this at the console

```bash
cd /var/www/pterodactyl
```

Step 7: Execute this at the console

```bash
php artisan down
```

Step 8: Execute this at the console

```bash
curl -L -o panel.tar.gz https://github.com/jexactyl/jexactyl/releases/latest/download/panel.tar.gz
```

Step 9: Execute this at the console

```bash
tar -xzvf panel.tar.gz && rm -f panel.tar.gz
```

Step 10: Execute this at the console

```bash
chmod -R 755 storage/* bootstrap/cache
```

Step 11: Execute this at the console (Enter yes if asked)

```bash
composer require asbiin/laravel-webauthn
```

Step 12: Execute this at the console (Enter yes if asked)

```bash
composer install --no-dev --optimize-autoloader
```

Step 13: Execute this at the console

```bash
php artisan optimize:clear
```

Step 14: Execute this at the console

```bash
php artisan migrate --seed --force
```

Step 15: Execute this at the console

```bash
chown -R www-data:www-data /var/www/pterodactyl/*
```

Step 16: Execute this at the console

```bash
php artisan queue:restart
```

Step 17: Execute this at the console

```bash
php artisan up
```

## Done! You have installed Jexactyl!
