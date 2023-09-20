package;

import openfl.display.Sprite;
import openfl.display.SimpleButton;
import openfl.text.TextField;
import openfl.geom.Rectangle;
import openfl.Assets;

class Main extends Sprite {

	private var textField:TextField;

	public function new() {
		super();

		var tab1Button = new SimpleButton();
		var tab2Button = new SimpleButton();
		var tab3Button = new SimpleButton();

		initButton(tab1Button, "Tab 1", 50, 20);
		initButton(tab2Button, "Tab 2", 150, 20);
		initButton(tab3Button, "Tab 3", 250, 20);

		textField = new TextField();
		textField.x = 50;
		textField.y = 100;
		textField.width = 300;
		textField.height = 2000; 
		textField.wordWrap = true;
		textField.multiline = true;

		// Setting the ScrollRect for initial visible area
		textField.scrollRect = new Rectangle(0, 0, 300, 200);

		addChild(textField);

		tab1Button.addEventListener(openfl.events.MouseEvent.CLICK, function(e) {
			textField.text = Assets.getText("assets/tab1.txt");
			resetScroll();
		});

		tab2Button.addEventListener(openfl.events.MouseEvent.CLICK, function(e) {
			textField.text = Assets.getText("assets/tab2.txt");
			resetScroll();
		});

		tab3Button.addEventListener(openfl.events.MouseEvent.CLICK, function(e) {
			textField.text = Assets.getText("assets/tab3.txt");
			resetScroll();
		});


		textField.addEventListener(openfl.events.MouseEvent.MOUSE_WHEEL, onScroll);
	}

	function initButton(button:SimpleButton, label:String, x:Float, y:Float):Void {
		var textField = new TextField();
		textField.text = label;
		button.upState = textField;
		button.overState = textField;
		button.downState = textField;
		button.hitTestState = textField;
		button.x = x;
		button.y = y;
		addChild(button);
	}

	private function onScroll(event:openfl.events.MouseEvent):Void {
		var newY = textField.scrollRect.y - event.delta * 10;
		newY = Math.max(0, Math.min(newY, textField.height - 200));
		var rect = textField.scrollRect.clone();
		rect.y = newY;
		textField.scrollRect = rect;
	}

	private function resetScroll():Void {
		var rect = textField.scrollRect.clone();
		rect.y = 0;
		textField.scrollRect = rect;
	}
}
