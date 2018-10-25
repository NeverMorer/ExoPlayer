# ExoPlayer #

[https://github.com/google/ExoPlayer](http://daringfireball.net/projects/markdown/syntax)

Add interposition function to set which DownloadAction can be download first.

Usage:

	public static void startWithActionImmediately(
	          Context context,
	          Class<? extends DownloadService> clazz,
	          DownloadAction downloadAction,
	          boolean foreground) {
	    Intent intent = buildAddActionIntent(context, clazz, downloadAction, foreground);
	    intent.putExtra(KEY_INTERPOSITION, true)
	    if (foreground) {
	      Util.startForegroundService(context, intent);
	    } else {
	      context.startService(intent);
	    }
	}