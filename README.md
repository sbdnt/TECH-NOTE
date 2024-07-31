# POST DATA WORKFLOW

## 001.Request send from client


## 002.Middleware class
    ```python
    "corsheaders.middleware.CorsMiddleware",
    "django.middleware.security.SecurityMiddleware",
    "django.contrib.sessions.middleware.SessionMiddleware",
    "django.middleware.common.CommonMiddleware",
    "django.middleware.csrf.CsrfViewMiddleware",
    "django.contrib.auth.middleware.AuthenticationMiddleware",
    "django.contrib.messages.middleware.MessageMiddleware",
    "django.middleware.clickjacking.XFrameOptionsMiddleware",
    "oauth2_provider.middleware.OAuth2TokenMiddleware",
    "django_user_agents.middleware.UserAgentMiddleware",
    "app.core.context.AppContextMiddleware",
    "app.devices.middleware.DeviceIDLoggerMiddleware",
    ....
    
    ```python


## 003.URL dispatcher




