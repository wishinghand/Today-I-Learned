Create a folder /site/tags/ and save this as snippet.php

`<?php
kirbytext::$tags['snippet'] = array(
  'attr' => array(
  ),
  'html' => function($tag) {
    $file =  $tag->attr('snippet');
    return snippet($file, array(), true);
  }
);`

To invoke it in your kirbytext field, type:

`(snippet: my-snippet)`