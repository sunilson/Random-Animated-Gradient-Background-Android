# 🌈 Random Animated Gradient Background for Android Views 🌈

To get an animated gradient as a background of any View you just need an AnimationList of GradientDrawable's

## Example

TODO

## Code

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
  
  //Add to animDrawable with animation duration
  animDrawable.addFrame(gradient, 4000)
}

//Apply to View
view.background = animDrawable

//Start animation. Enter duration should be half the animation duration
animDrawable.setEnterFadeDuration(2000)
animDrawable.setExitFadeDuration(4000)
animDrawable.start()

```

That's it. This can be applied to any view, for example to all views in a Recyclerview (use in onViewAttachedToWindow)

The color and orientation list could look like this for example: 

```
val COLORS = listOf(
            Color.parseColor("#7986CB") to Color.parseColor("#D50000"),
            Color.parseColor("#E91E63") to Color.parseColor("#7B1FA2"),
            Color.parseColor("#00BCD4") to Color.parseColor("#C0CA33"),
            Color.parseColor("#FBC02D") to Color.parseColor("#795548"),
            Color.parseColor("#FF5722") to Color.parseColor("#9575CD"),
            Color.parseColor("#AD1457") to Color.parseColor("#EA80FC"),
            Color.parseColor("#26A69A") to Color.parseColor("#FF6F00"),
            Color.parseColor("#8BC34A") to Color.parseColor("#FF8F00")
        )
    
val ORIENTATIONS = listOf(
            GradientDrawable.Orientation.TL_BR,
            GradientDrawable.Orientation.BL_TR,
            GradientDrawable.Orientation.BR_TL,
            GradientDrawable.Orientation.TR_BL)
```
