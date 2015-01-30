# RMParallax
The way to impress users on the first app launch.

Created by Raphael Miller and Michael Babiy.

If you are looking for a nice way to introduce the features of your app, this control is for you. In addition to paging through images with a nice parallax effect, RMParallax also creates a nice transition for your "description" text. As an added bonus, you can also add motion effect to your pages by simply setting motion:true.

RMParallax is simple to use. All you have to do is create RMParallaxItem:

```
let item1 = RMParallaxItem(image: UIImage(named: "item1")!, text: "SHARE LIGHTBOXES WITH YOUR TEAM")
let item2 = RMParallaxItem(image: UIImage(named: "item2")!, text: "FOLLOW WORLD CLASS PHOTOGRAPHERS")
let item3 = RMParallaxItem(image: UIImage(named: "item3")!, text: "EXPLORE OUR COLLECTION BY CATEGORY")
```

Create RMParallax controller with items you created earlier:

```
let rmParallaxViewController = RMParallax(items: [item1, item2, item3], motion: false)
        rmParallaxViewController.completionHandler = {
            UIView.animateWithDuration(0.4, animations: { () -> Void in
                rmParallaxViewController.view.alpha = 0.0
            })
        }
```

Add your RMParallax controller to the view controller:

```
// Adding parallax view controller.
        self.addChildViewController(rmParallaxViewController)
        self.view.addSubview(rmParallaxViewController.view)
        rmParallaxViewController.didMoveToParentViewController(self)
```

RMParallax uses closures to notify presenting view controller when the user is done paging through. This is a perfect spot to save response, dismiss, or do whatever you like.

Please checkout included sample project. 

Special thanks to the team at Getty Images whom I greatly respect.

Thanks.