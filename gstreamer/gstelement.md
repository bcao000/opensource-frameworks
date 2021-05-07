```
/* we define this to avoid a compiler warning regarding a cast from a function
 * pointer to a void pointer
 * (see https://bugzilla.gnome.org/show_bug.cgi?id=309253)
 */
typedef	void (* GstDebugFuncPtr)	(void);
```
```
#define GST_DEBUG_FUNCPTR(ptr) (_gst_debug_register_funcptr((GstDebugFuncPtr)(ptr), #ptr) , ptr)
GST_DEBUG_FUNCPTR:
Expands to:

(_gst_debug_register_funcptr((GstDebugFuncPtr)(gst_element_set_state_func), "gst_element_set_state_func") , gst_element_set_state_func)
```
