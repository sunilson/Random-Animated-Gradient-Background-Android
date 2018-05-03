# 🌈 Random Animated Gradient Background for Android Views 🌈

To get an animated gradient as a background of any View you just need an AnimationList of GradientDrawable's

##Example

TODO

##Code

```
//Get the view that should get the background
val view = ...

//Create an Animation Drawable
val animDrawable = AnimationDrawable()

//Iterate over as many gradients as you want to add
for(i in 0..2) {
  //Get two random colors as list
  val colors = listof(color1, color2)
  
  //Get a random orientation (gradient angle) from GradientDrawable.Orientation
  val orientation = ...
  
  //Create gradient
  val gradient = GradientDrawable(orientation, colors.toIntArray())
  
  //Add to animDrawable
  animDrawable.addFrame(gradient, 4000)
}

//Apply to View
view.background = animDrawable

//Start animation
animDrawable.setEnterFadeDuration(2000)
animDrawable.setExitFadeDuration(4000)
animDrawable.start()

```

That's it. This can be applied to any view, for example to all views in a Recyclerview (use in onViewAttachedToWindow)
