main()
    - config
    - health
        * /status
        * /health
        * /__version__
        * /__heartbeat__
        * /__lbheartbeat__
    - db
    - metrics
    + web
        - auth
        - handlers
            * WebPushHandler - r"/wpush/(?:(?P<api_ver>v\d+)\/)?(?P<token>[^\/]+)"
            * MessageHandler - r"/m/(?P<message_id>[^\/]+)"
            * NewRegistrationHandler - r"/v1/(?P<type>[^\/]+)/(?P<app_id>[^\/]+)/registration"
            * UaidRegistrationHandler - r"/v1/(?P<type>[^\/]+)/(?P<app_id>[^\/]+)/registration/(?P<uaid>[^\/]+)"
            * SubRegistrationHandler - r"/v1/(?P<type>[^\/]+)/(?P<app_id>[^\/]+)/registration/(?P<uaid>[^\/]+)/subscription"
            * ChannelRegistrationHandler - r"/v1/(?P<type>[^\/]+)/(?P<app_id>[^\/]+)/registration/(?P<uaid>[^\/]+)/subscription/(?P<chid>[^\/]+)"
            * LogCheckHandler - r"/v1/err(?:/(?P<err_type>[^\/]+))?"
    + routers
        + GCM
        + FCM
        + APNs
        + ADM
        + WebPush
