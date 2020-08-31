# EnvConfig

Organize configs in a clean way.

## Getting Started

1. Install the library.

   ```bash
   go get github.com/short-d/envconfig
   ```

1. Parse configs from environmental variables.

   ```go
   import "github.com/short-d/envconfig"
   
   envConfig := envconfig.NewDefault()

   config := struct {
       DBHost     string `env:"DB_HOST" default:"localhost"`
       DBPort     int    `env:"DB_PORT" default:"5432"`
       DBUser     string `env:"DB_USER" default:"postgres"`
       DBPassword string `env:"DB_PASSWORD" default:"password"`
       DBName     string `env:"DB_NAME" default:"sampleapp"`
   }{}
   err := envConfig.ParseConfigFromEnv(&config)
   if err != nil {
       panic(err)
   }
   ```

## License

This project is maintained under MIT license.
