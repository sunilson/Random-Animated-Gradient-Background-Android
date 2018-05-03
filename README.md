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

The color and orientation list could look like this for example: 

```
val COLORS = listOf(
            Pair(Color.parseColor("#7986CB"), Color.parseColor("#D50000")),
            Pair(Color.parseColor("#E91E63"), Color.parseColor("#7B1FA2")),
            Pair(Color.parseColor("#00BCD4"), Color.parseColor("#C0CA33")),
            Pair(Color.parseColor("#FBC02D"), Color.parseColor("#795548")),
            Pair(Color.parseColor("#FF5722"), Color.parseColor("#9575CD")),
            Pair(Color.parseColor("#AD1457"), Color.parseColor("#EA80FC")),
            Pair(Color.parseColor("#26A69A"), Color.parseColor("#FF6F00")),
            Pair(Color.parseColor("#8BC34A"), Color.parseColor("#FF8F00")))
    
val ORIENTATIONS = listOf(
            GradientDrawable.Orientation.TL_BR,
            GradientDrawable.Orientation.BL_TR,
            GradientDrawable.Orientation.BR_TL,
            GradientDrawable.Orientation.TR_BL)
```
