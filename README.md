IPhoneFileUploadServer
======================

IPhoneFileUploadServer with cocoahttpserver
use arc

mail me :ygweric@gmail.com

refer to https://github.com/robbiehanson/CocoaHTTPServer


2013-06-13 ++++++++++++
add a notification to post http server port

HOW USE:<br/>
use it with 2 step:<br/>
1\in you UIViewController's -viewDidLoad(),do that:<br/>
<pre><code>
- (void)viewDidLoad
{
    [super viewDidLoad];
	NSNotificationCenter *nc=[NSNotificationCenter defaultCenter];
    [nc addObserver:self selector:@selector(handlerPortSuccess:) name:@"HTTPServer_get_port_success" object:nil];
    [nc addObserver:self selector:@selector(handlerPortFail:) name:@"HTTPServer_get_port_fail" object:nil];
    //........
}
</code></pre>
2\And realize 2 method<br/>
<pre><code>
-(void)handlerPortSuccess:(NSNotification *)notification{
    NSDictionary* userInfo=notification.userInfo;
    NSNumber* port=[userInfo valueForKey:@"local_port"];
    NSLog(@"handlerPortSuccess----port:%d",port.unsignedShortValue);
}

-(void)handlerPortFail:(NSNotification *)notification{
    NSLog(@"handlerPortFail-----");
}
</code></pre>
ok, that all ,enjoy it


