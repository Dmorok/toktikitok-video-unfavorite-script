# toktikitok-video-unfavorite-script
chrome console code


function simulateKeyPress(keyCode) {
  var event = new KeyboardEvent('keydown', { keyCode: keyCode });
  document.dispatchEvent(event);
}

function clickButtonByXPath(xpath) {
  var button = document.evaluate(xpath, document, null, XPathResult.FIRST_ORDERED_NODE_TYPE, null).singleNodeValue;
  if (button) {
    button.click();
  }
}

async function simulateActions() {
  var xpath1 = '/html/body/div[1]/div[3]/div[4]/div/div[2]/div[2]/div[3]/div[1]/div[1]/button[3]';
  var xpath2 = '/html/body/div[1]/div[3]/div[4]/div/div[1]/button[3]';
  var repeatCount = 100;

  for (var i = 0; i < repeatCount; i++) {
    clickButtonByXPath(xpath1);
    clickButtonByXPath(xpath2);
    await new Promise(resolve => setTimeout(resolve, 1000));
  }
}

simulateActions();
