<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>JQueryの練習</title>
</head>
<body>
  <p>JQuery</p>
  <ul id="main">
    <li>0</li>
    <li class= "item">1</li>
    <li class= "item">2</li>
    <li>
      3
      <ul id="sub">
        <li>3-0</li>
        <li>3-1</li>
        <li class= "item">3-2</li>
        <li class= "item">3-3</li>
        <li>3-4</li>
      </ul>
    </li>
  </ul>
  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script>
    $("#sub > li:eq(2)").siblings().css('color', 'blue');
  </script>
</body>

</html>









<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>JQueryの練習</title>
</head>
<body>
  <p>JQuery</p>
  <p><a href="http://google.com">Google</a></p>
  <p><a href="http://yahoo.co.jp">Yahoo!</a></p>
  <p><a href="http://dotinstall.com">Dotinstall</a></p>

  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script>
    $(function(){
      $('a[href$=com]').css('background', 'skyblue');
      $('a[href*=google]').css('background', 'skyblue');
    });
  </script>
</body>

</html>








<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>JQueryの練習</title>
  <style>
    .myStyle {
      border: 5px solid green;
      font-size: 48px;
    }
  </style>
</head>
<body>
  <p>JQuery</p>

  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script>
    $(function(){
      // $('p').css('color', 'brown').css('background', 'pink');
      // console.log($('p').css('color'));

      $('p').addClass('myStyle');

    });
  </script>
</body>

</html>












<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>JQueryの練習</title>
</head>
<body>
  <p>JQuery</p>
  <a href="http://google.com" data-sitename="google">Google</a>
  <input type="text" value="hello">

  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script>
    $(function() {
      // console.log($('a').attr('href'));
      // $('a').attr('href', 'http://google.co.jp');
      // console.log($('a').data('sitename'));
      // $('p').text('Just Changed');
      // $('p').html('<a href="">click me!</a>');
      // console.log($('input').val());
      // $('input').val('hello, again!');
      // $('p').empty();
      $('p').remove();
    });
  </script>
</body>

</html>












<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>JQueryの練習</title>
</head>
<body>
  <p>JQuery</p>
  <ul>
    <li>0</li>
    <li>1</li>
    <li>2</li>
  </ul>
  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script>
    $(function() {
      var li = $('<li>').text('just added');
      // $('ul > li:eq(1)').before(li);
      // li.insertBefore($('ul > li:eq(1)'));
      // $('ul').prepend(li);
      li.appendTo($('ul'));
    });
  </script>
</body>
</html>





<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>JQueryの練習</title>
</head>
<body>
  <p>JQuery</p>
  <div id="box" style="width:100px; height:100px; background:red;"></div>
  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script>
    $(function() {
      // $('#box').hide('800');
      // $('#box').fadeOut(800);
      // $('#box').toggle(800);
      // $('#box').fadeOut(800, function() {
      //   alert("gone!");
      // });

      $('#box').click(function() {
        alert("hi!");
      })
      $('#box')
      .mouseover(function() {
        $(this).css('background','green');
      })
      .mouseout(function() {
        $(this).css('background','red');
      })
      .mousemove(function(e) {
        $(this).text(e.pageX);
      })

    });
  </script>
</body>
</html>













<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>JQueryの練習</title>
</head>
<body>
  <p>JQuery</p>
  <input type="text" id="name">
  <select id="members" name="members">
    <option>taguchi</option>
    <option>fkoji</option>
    <option>dotinstall</option>
  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script>
    $(function() {
      $('#name')
       .focus(function() {
         $(this).css('background', 'lightgreen');
       })
       .blur(function() {
         $(this).css('background', 'white');
       });
      $('#members').change(function() {
        alert('changed!');
      });

    });
  </script>
</body>
</html>









<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>JQueryの練習</title>
</head>
<body>
  <p>JQuery</p>
  <button>Add!</button>
  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script>
    $(function() {

      $('button').click(function() {
        var p = $('<p>').text('vanish!').addClass('vanish');
        $(this).before(p);
      });

      $('body').on('click', '.vanish', function() {
        $(this).remove();
      });
    });
  </script>
</body>
</html>





<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>JQueryの練習</title>
</head>
<body>
  <p>JQuery</p>
  <button>もっと読む</button>
  <div id="result"></div>

  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script>
    $(function() {
      $('button').click(function() {
        $('#result').load('more.html', function {
          $('message').css('color', 'red');
      });
    });
  </script>
</body>
</html>








<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>JQueryの練習</title>
</head>
<body>
  <p>JQuery</p>

  <p>
    <input type="text" name="name" id="name">
    <input type="button" id="greet" value="Greet!">
  </p>
  <div id="result"></div>

  <script src="https://code.jquery.com/jquery-3.3.1.min.js"></script>
  <script>
    $(function() {
      $('#greet').click(function() {
       $.get('greet.php', {
         name: $('#name').val()
       }, function(data) {
         $('#result').html(data.message + '(' + data.length + ')');
       });
      });
    });
  </script>
</body>
</html>






<?php

// echo htmlspecialchars("hi!" . $.GET['name'], ENT_QUOTES, "utf-8");

$rs = array(
  "message" => htmlspecialchars("hi!" . $.GET['name'], ENT_QUOTES, "utf-8")
  "length" => strlen($_GET['name'])
);

header('Content-Type: application/jason; charset=utf-8');
echo json_encode($rs);






