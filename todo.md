场景：

有多个输入框输入同一个属性，比如学校，每个功能点都需要根据特定的条件来 请求不同的地址 


```
var schoolEngine = new Bloolhound({
    'identity': function(obj) {return obj.id},
    'queryTokenizer': Bloodhound.tokenizers.whitespace,
    'datumTokenizer': Bloodhound.tokenizers.obj.whitespace('id'),
    'remote': {
        url: 'data.json',
        prepare: function(query, transport) {
            transport.url = transport.url + '?q=' + $('#id').val();
            return transport;
        }
    }
});
```

[example](scenario1/index.html)
