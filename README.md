# web
webview 一些权限整理


        //应用缓存API是否可用，默认值false, 结合setAppCachePath(String)使用。
        s.setAppCacheEnabled(true);
        //设置应用缓存文件的路径。
        s.setAppCachePath("");
        
        // 设置是否允许通过 file url 加载的 Javascript 可以访问其他的源(包括http、https等源)
        //4.1以后默认禁止
        s.setAllowUniversalAccessFromFileURLs(false);
        // 设置是否允许通过 file url 加载的 Js代码读取其他的本地文件
        //4.1以后默认禁止
        s.setAllowFileAccessFromFileURLs(true);
        // 是否允许访问文件，默认允许。注意，这里只是允许或禁止对文件系统的访问
        // Assets 和 resources 文件使用file:///android_asset和file:///android_res仍是可访问的。
        s.setAllowFileAccess(true);
        //是否允许在WebView中访问内容URL（Content Url），默认允许
        s.setAllowContentAccess(true);

        //是否禁止从网络（通过http和https URI schemes访问的资源）下载图片资源，默认值为false 不禁止。
        s.setBlockNetworkImage(true);
        //是否禁止从网络下载数据，如果app有INTERNET权限，默认值为false，否则默认为true。
        s.setBlockNetworkLoads(true);
        //是否使用内置的缩放机制。默认值为false。
        s.setBuiltInZoomControls(true);
        //使用内置的缩放机制时是否展示缩放控件，默认值true。
        s.setDisplayZoomControls(true);

        //重写使用缓存的方式，默认值LOAD_DEFAULT。
        s.setCacheMode(WebSettings.LOAD_DEFAULT);
        //设置WebView字体库字体，默认“cursive”
        s.setCursiveFontFamily("");

        //数据库存储API是否可用，默认值false。如何正确设置数据存储API参见setDatabasePath(String)。
        s.setDatabaseEnabled(true);
        //设置默认固定的字体大小，默认为16，可取值1到72
        s.setDefaultFixedFontSize(1);
        //设置默认的字体大小，默认16，可取值1到72
        s.setDefaultFontSize(1);
        //设置默认的字符编码集，默认”UTF-8”.
        s.setDefaultTextEncodingName("utf-8");
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.N) {
            s.setDisabledActionModeMenuItems(WebSettings.MIXED_CONTENT_ALWAYS_ALLOW);
        }
        //DOM存储API是否可用，默认false。
        s.setDomStorageEnabled(true);

        //设置fantasy字体集（font family）的名字默认为“fantasy”
        s.setFantasyFontFamily("");
        //设置固定的字体集的名字，默认为”monospace”。
        s.setFixedFontFamily("");

        //定位是否可用，默认为true。
        //(1) app必须有定位的权限，参见ACCESS_COARSE_LOCATION, ACCESS_FINE_LOCATION；
        //(2) app必须提供onGeolocationPermissionsShowPrompt(String, GeolocationPermissions.Callback)回调方法的实现，
        // 在页面通过JavaScript定位API请求定位时接收通知。
        //作为可选项，可以在数据库中存储历史位置和Web初始权限，参见setGeolocationDatabasePath(String).
        s.setGeolocationEnabled(true);
        //定位数据库的保存路径，为了确保定位权限和缓存位置的持久化，该方法应该传入一个应用可写的路径。
        s.setGeolocationDatabasePath("");

        //让JavaScript自动打开窗口，默认false。
        s.setJavaScriptCanOpenWindowsAutomatically(true);
        //设置WebView是否允许执行JavaScript脚本，默认false，不允许。
        s.setJavaScriptEnabled(true);

        //设置布局，会引起WebView的重新布局（relayout）,默认值NARROW_COLUMNS
        s.setLayoutAlgorithm(WebSettings.LayoutAlgorithm.NORMAL);
        //WebView是否下载图片资源，默认为true。注意，该方法控制所有图片的下载，
        s.setLoadsImagesAutomatically(true);
        //是否允许WebView度超出以概览的方式载入页面，默认false。即缩小内容以适应屏幕宽度。
        s.setLoadWithOverviewMode(true);

        //WebView是否需要用户的手势进行媒体播放，默认值为true。
        s.setMediaPlaybackRequiresUserGesture(true);
        //设置最小的字号，默认为8
        s.setMinimumFontSize(1);
        //设置最小的本地字号，默认为8。
        s.setMinimumLogicalFontSize(1);
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.LOLLIPOP) {
            //当一个安全的来源（origin）试图从一个不安全的来源加载资源时配置WebView的行为。
            //LOLLIPOP版本默认值MIXED_CONTENT_NEVER_ALLOW，
            s.setMixedContentMode(1);
        }

        //调用requestFocus(int, android.graphics.Rect)时是否需要设置节点获取焦点，默认值为true
        s.setNeedInitialFocus(true);

        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.M) {
            //当WebView切换到后台但仍然与窗口关联时是否raster tiles，
            // 打开它可以避免在WebView从后台切换到前台时重新绘制，默认值false。
            s.setOffscreenPreRaster(true);
        }

        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.O) {
            //设置安全浏览默认为true
            s.setSafeBrowsingEnabled(true);
        }
        //设置无衬线字体集（sans-serif font family）的名字。默认值”sans-serif”.
        s.setSansSerifFontFamily("");
        //WebView是否保存表单数据，默认值true。
        s.setSaveFormData(true);
        //设置衬线字体集（serif font family）的名字，默认“sans-serif”。
        s.setSerifFontFamily("");
        //设置WebView是否支持多窗口。如果设置为true，
        // 主程序要实现onCreateWindow(WebView, boolean, boolean, Message)，默认false。
        s.setSupportMultipleWindows(true);
        //设置标准字体集的名字，默认值“sans-serif”。
        s.setStandardFontFamily("");
        //WebView是否支持使用屏幕上的缩放控件和手势进行缩放，默认值true。
        s.setSupportZoom(true);

        //设置页面上的文本缩放百分比，默认100。
        s.setTextZoom(1);

        //设置WebView的用户代理字符串。
        s.setUserAgentString("");
        ////WebView是否支持HTML的“viewport”标签或者使用wide viewport。
        s.setUseWideViewPort(true);


        //已废弃。设置应用缓存内容的最大值。
        s.setAppCacheMaxSize(100l);
        //已废弃，数据库路径由实现（implementation）管理，调用此方法无效。
        s.setDatabasePath("");
        s.setDefaultZoom(WebSettings.ZoomDensity.MEDIUM);
       //已废弃，将来会成为空操作（no-op
        s.setEnableSmoothTransition(true);

        //已废弃。从 JELLY_BEAN 开始，该设置无效。允许使用轻触摸做出选择和光标悬停。`
        s.setLightTouchEnabled(true);
        //在API18以上已废弃。未来将不支持插件，不要使用。
        s.setPluginState(WebSettings.PluginState.ON);
        //在API18以上已废弃。不建议调整线程优先级，未来版本不会支持这样做。
        s.setRenderPriority(WebSettings.RenderPriority.HIGH);
        //API18以上版本已废弃。
        s.setSavePassword(true);
        //API14版本以上已废弃。请取代使用setTextZoom(int)。设置页面文本的尺寸，默认NORMAL。
        s.setTextSize(WebSettings.TextSize.SMALLEST);
