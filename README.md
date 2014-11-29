 function RandomPos(){
 
 
 $(".cardimage").remove();
    ballLeftPos = [];
    ballTopPos = [];
    for (var num=0;num<ballNum;num++){
	var obj = $('<div class="cardimage" id="img'+num+'"><img src="images/img_'+num+'.png" width="49" height="64"/></div>');   
	$('#shoeContainer').append(obj);
	objWidth=obj.width();
	objHeight=obj.height();
    var pageWidth=$('#shoeContainer').width();
    var pageHeight=$('#shoeContainer').height();
    var leftPos, topPos;
    do{
	leftPos = Math.random()*(pageWidth-objWidth);
	topPos = Math.random()*(pageHeight-objHeight);
    }
    while (isOverlaped(leftPos, topPos))
    ballLeftPos.push(leftPos);
    ballTopPos.push(topPos);
    obj.css({left:ballLeftPos[num]+"px", top:ballTopPos[num]+"px"});
    posObjArr.push({"left":leftPos,"top":topPos});
    applydraggble();
    }
    }
