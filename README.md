# შეტყობინება ინტერნეტთან კავშირის შესახებ Bootstrap 4 & javascript
[![TicciX Copyright](https://i.imgur.com/7S2IFBc.png)](https://github.com/Ticcix/) [![TicciX Copyright](https://camo.githubusercontent.com/4e46825f5519748c0efc0f74e7227de0579ce4c6/68747470733a2f2f692e696d6775722e636f6d2f4f77594b6f56622e706e67)](https://ticcix.github.io/toast_demo/)
<pre class="code code-html"><code>&lt;div class="toast" style="position: absolute; top: 25px; right: 25px;"&gt;
    &lt;div class="toast-header"&gt;
        &lt;i class="bi bi-wifi"&gt;&lt;/i&gt;&amp;nbsp;&amp;nbsp;&amp;nbsp;
        &lt;strong class="mr-auto"&gt;&lt;span class="text-success"&gt;ინტერნეტთან კავშირი აღდგა&lt;/span&gt;&lt;/strong&gt;
        &lt;button type="button" class="ml-2 mb-1 close" data-dismiss="toast" aria-label="Close"&gt;
            &lt;span aria-hidden="true"&gt;&amp;times;&lt;/span&gt;
        &lt;/button&gt;
    &lt;/div&gt;
    &lt;div class="toast-body"&gt;
        ინტერნეტი ჩართულია.
    &lt;/div&gt;
&lt;/div&gt;

&lt;script&gt;

var status = 'online';
var current_status = 'online';

function check_internet_connection()
{
    if(navigator.onLine)
    {
        status = 'online';
    }
    else
    {
        status = 'offline';
    }

    if(current_status != status)
    {
        if(status == 'online')
        {
            $('i.bi').addClass('bi-wifi');
            $('i.bi').removeClass('bi-wifi-off');
            $('.mr-auto').html("&lt;span class='text-success'&gt;ინტერნეტთან კავშირი აღდგა&lt;/span&gt;");
            $('.toast-body').text('ინტერნეტი ჩართულია.');
        }
        else
        {
            $('i.bi').addClass('bi-wifi-off');
            $('i.bi').removeClass('bi-wifi');
            $('.mr-auto').html("&lt;span class='text-danger'&gt;ინტერნეტთან კავშირი განწყდა&lt;/span&gt;");
            $('.toast-body').text('შეამოწმეთ შეერთება.')
        }

        current_status = status;

        $('.toast').toast({
            autohide: false
        });

        $('.toast').toast('show');
    }
}

check_internet_connection();

setInterval(function(){
    check_internet_connection();
}, 1000);

&lt;/script&gt;</code></pre>
