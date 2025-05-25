  * tracking my learnings from looking through the code:research pairs
    * [[2024-02-10]]
      * checked out hasKey jsBinding hat cdata mentioned in discord. That macro "#[wasm_bindgen(js_name = "hasKey")]" combined with errthing else in file basically maps the rust has_key method to js.
      * noticed it looks like even constructor for NoosphereContext needs js binding - i assume that's what "pub fn new" is. Wonder if required to use that class/struct at all (like any method). Also, i noticed JS binding has to use a lot more code - i wonder why