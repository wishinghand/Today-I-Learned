javascript functions:

function ajaxLoad(uri, callback, params){
    var request = (window.XMLHttpRequest) ? new XMLHttpRequest() : new ActiveXObject("Microsoft.XMLHTTP");
    request.onreadystatechange = callback;
    request.open("POST", uri,true);

    request.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
    //request.setRequestHeader("Content-length", params.length);
    //request.setRequestHeader("Connection", "close");
    request.send(params);
}

function callback(evt){
    if(evt.currentTarget.readyState == 4){
        var returnObject = JSON.parse(evt.currentTarget.responseText);
    }
}