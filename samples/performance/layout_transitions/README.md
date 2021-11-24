### Layout transitions<br/>
Vulkan requires the application to manage image layouts, so that all render pass attachments are in the correct layout when the render pass begins. This is usually done using pipeline barriers or the `initialLayout` and `finalLayout` parameters of the render pass. If the rendering pipeline is complex, transitioning each image to its correct layout is not trivial, as it requires some sort of state tracking. If previous image contents are not needed, there is an easy way out, that is setting `oldLayout`/`initialLayout` to `VK_IMAGE_LAYOUT_UNDEFINED`. While this is functionally correct, it can have performance implications as it may prevent the GPU from performing some optimizations. This sample will cover an example of such optimizations and how to avoid the performance overhead from using sub-optimal layouts.

- 🎓 [Choosing the correct layout when transitioning images](./layout_transitions_tutorial.md)