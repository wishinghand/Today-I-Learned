function titleCase(exampleString){
  var words = exampleString.split(' ')
  var titleCasedWords = words.map((word) => {
    return word[0].toUpperCase() + word.substring(1);
  })
  return titleCasedWords.join(' ')
}