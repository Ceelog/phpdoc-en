Newt
====

**Table of Contents**

-   [Introduction](/intro/newt.html)
-   [Installing/Configuring](/newt/setup.html)
    -   [Requirements](/newt/setup.html#Requirements)
    -   [Installation](/newt/setup.html#Installation)
    -   [Runtime
        Configuration](/newt/setup.html#Runtime%20Configuration)
    -   [Resource Types](/newt/setup.html#Resource%20Types)
-   [Predefined Constants](/newt/constants.html)
    -   [Newt form exit
        reasons](/newt/constants.html#Newt%20form%20exit%20reasons)
    -   [Newt colorsets](/newt/constants.html#Newt%20colorsets)
    -   [Newt argument
        flags](/newt/constants.html#Newt%20argument%20flags)
    -   [Newt Flags Sense](/newt/constants.html#Newt%20Flags%20Sense)
    -   [Newt Components
        Flags](/newt/constants.html#Newt%20Components%20Flags)
    -   [File Descriptor
        Flags](/newt/constants.html#File%20Descriptor%20Flags)
    -   [Checkbox Tree
        Flags](/newt/constants.html#Checkbox%20Tree%20Flags)
    -   [Entry Flags](/newt/constants.html#Entry%20Flags)
    -   [Listbox Flags](/newt/constants.html#Listbox%20Flags)
    -   [Textbox Flags](/newt/constants.html#Textbox%20Flags)
    -   [Form Flags](/newt/constants.html#Form%20Flags)
    -   [Newt Keys](/newt/constants.html#Newt%20Keys)
    -   [Newt Anchors](/newt/constants.html#Newt%20Anchors)
    -   [Grid Flags](/newt/constants.html#Grid%20Flags)
-   [Examples](/newt/examples.html)
    -   [Basic usage](/newt/examples.html#Basic%20usage)
-   [Newt Functions](/ref/newt.html)
    -   [newt\_bell](/ref/newt.html#newt_bell) — Send a beep to the
        terminal
    -   [newt\_button\_bar](/ref/newt.html#newt_button_bar) — This
        function returns a grid containing the buttons created
    -   [newt\_button](/ref/newt.html#newt_button) — Create a new button
    -   [newt\_centered\_window](/ref/newt.html#newt_centered_window) —
        Open a centered window of the specified size
    -   [newt\_checkbox\_get\_value](/ref/newt.html#newt_checkbox_get_value)
        — Retreives value of checkox resource
    -   [newt\_checkbox\_set\_flags](/ref/newt.html#newt_checkbox_set_flags)
        — Configures checkbox resource
    -   [newt\_checkbox\_set\_value](/ref/newt.html#newt_checkbox_set_value)
        — Sets the value of the checkbox
    -   [newt\_checkbox\_tree\_add\_item](/ref/newt.html#newt_checkbox_tree_add_item)
        — Adds new item to the checkbox tree
    -   [newt\_checkbox\_tree\_find\_item](/ref/newt.html#newt_checkbox_tree_find_item)
        — Finds an item in the checkbox tree
    -   [newt\_checkbox\_tree\_get\_current](/ref/newt.html#newt_checkbox_tree_get_current)
        — Returns checkbox tree selected item
    -   [newt\_checkbox\_tree\_get\_entry\_value](/ref/newt.html#newt_checkbox_tree_get_entry_value)
        — Description
    -   [newt\_checkbox\_tree\_get\_multi\_selection](/ref/newt.html#newt_checkbox_tree_get_multi_selection)
        — Description
    -   [newt\_checkbox\_tree\_get\_selection](/ref/newt.html#newt_checkbox_tree_get_selection)
        — Description
    -   [newt\_checkbox\_tree\_multi](/ref/newt.html#newt_checkbox_tree_multi)
        — Description
    -   [newt\_checkbox\_tree\_set\_current](/ref/newt.html#newt_checkbox_tree_set_current)
        — Description
    -   [newt\_checkbox\_tree\_set\_entry\_value](/ref/newt.html#newt_checkbox_tree_set_entry_value)
        — Description
    -   [newt\_checkbox\_tree\_set\_entry](/ref/newt.html#newt_checkbox_tree_set_entry)
        — Description
    -   [newt\_checkbox\_tree\_set\_width](/ref/newt.html#newt_checkbox_tree_set_width)
        — Description
    -   [newt\_checkbox\_tree](/ref/newt.html#newt_checkbox_tree) —
        Description
    -   [newt\_checkbox](/ref/newt.html#newt_checkbox) — Description
    -   [newt\_clear\_key\_buffer](/ref/newt.html#newt_clear_key_buffer)
        — Discards the contents of the terminal's input buffer without
        waiting for additional input
    -   [newt\_cls](/ref/newt.html#newt_cls) — Description
    -   [newt\_compact\_button](/ref/newt.html#newt_compact_button) —
        Description
    -   [newt\_component\_add\_callback](/ref/newt.html#newt_component_add_callback)
        — Description
    -   [newt\_component\_takes\_focus](/ref/newt.html#newt_component_takes_focus)
        — Description
    -   [newt\_create\_grid](/ref/newt.html#newt_create_grid) —
        Description
    -   [newt\_cursor\_off](/ref/newt.html#newt_cursor_off) —
        Description
    -   [newt\_cursor\_on](/ref/newt.html#newt_cursor_on) — Description
    -   [newt\_delay](/ref/newt.html#newt_delay) — Description
    -   [newt\_draw\_form](/ref/newt.html#newt_draw_form) — Description
    -   [newt\_draw\_root\_text](/ref/newt.html#newt_draw_root_text) —
        Displays the string text at the position indicated
    -   [newt\_entry\_get\_value](/ref/newt.html#newt_entry_get_value) —
        Description
    -   [newt\_entry\_set\_filter](/ref/newt.html#newt_entry_set_filter)
        — Description
    -   [newt\_entry\_set\_flags](/ref/newt.html#newt_entry_set_flags) —
        Description
    -   [newt\_entry\_set](/ref/newt.html#newt_entry_set) — Description
    -   [newt\_entry](/ref/newt.html#newt_entry) — Description
    -   [newt\_finished](/ref/newt.html#newt_finished) — Uninitializes
        newt interface
    -   [newt\_form\_add\_component](/ref/newt.html#newt_form_add_component)
        — Adds a single component to the form
    -   [newt\_form\_add\_components](/ref/newt.html#newt_form_add_components)
        — Add several components to the form
    -   [newt\_form\_add\_hot\_key](/ref/newt.html#newt_form_add_hot_key)
        — Description
    -   [newt\_form\_destroy](/ref/newt.html#newt_form_destroy) —
        Destroys a form
    -   [newt\_form\_get\_current](/ref/newt.html#newt_form_get_current)
        — Description
    -   [newt\_form\_run](/ref/newt.html#newt_form_run) — Runs a form
    -   [newt\_form\_set\_background](/ref/newt.html#newt_form_set_background)
        — Description
    -   [newt\_form\_set\_height](/ref/newt.html#newt_form_set_height) —
        Description
    -   [newt\_form\_set\_size](/ref/newt.html#newt_form_set_size) —
        Description
    -   [newt\_form\_set\_timer](/ref/newt.html#newt_form_set_timer) —
        Description
    -   [newt\_form\_set\_width](/ref/newt.html#newt_form_set_width) —
        Description
    -   [newt\_form\_watch\_fd](/ref/newt.html#newt_form_watch_fd) —
        Description
    -   [newt\_form](/ref/newt.html#newt_form) — Create a form
    -   [newt\_get\_screen\_size](/ref/newt.html#newt_get_screen_size) —
        Fills in the passed references with the current size of the
        terminal
    -   [newt\_grid\_add\_components\_to\_form](/ref/newt.html#newt_grid_add_components_to_form)
        — Description
    -   [newt\_grid\_basic\_window](/ref/newt.html#newt_grid_basic_window)
        — Description
    -   [newt\_grid\_free](/ref/newt.html#newt_grid_free) — Description
    -   [newt\_grid\_get\_size](/ref/newt.html#newt_grid_get_size) —
        Description
    -   [newt\_grid\_h\_close\_stacked](/ref/newt.html#newt_grid_h_close_stacked)
        — Description
    -   [newt\_grid\_h\_stacked](/ref/newt.html#newt_grid_h_stacked) —
        Description
    -   [newt\_grid\_place](/ref/newt.html#newt_grid_place) —
        Description
    -   [newt\_grid\_set\_field](/ref/newt.html#newt_grid_set_field) —
        Description
    -   [newt\_grid\_simple\_window](/ref/newt.html#newt_grid_simple_window)
        — Description
    -   [newt\_grid\_v\_close\_stacked](/ref/newt.html#newt_grid_v_close_stacked)
        — Description
    -   [newt\_grid\_v\_stacked](/ref/newt.html#newt_grid_v_stacked) —
        Description
    -   [newt\_grid\_wrapped\_window\_at](/ref/newt.html#newt_grid_wrapped_window_at)
        — Description
    -   [newt\_grid\_wrapped\_window](/ref/newt.html#newt_grid_wrapped_window)
        — Description
    -   [newt\_init](/ref/newt.html#newt_init) — Initialize newt
    -   [newt\_label\_set\_text](/ref/newt.html#newt_label_set_text) —
        Description
    -   [newt\_label](/ref/newt.html#newt_label) — Description
    -   [newt\_listbox\_append\_entry](/ref/newt.html#newt_listbox_append_entry)
        — Description
    -   [newt\_listbox\_clear\_selection](/ref/newt.html#newt_listbox_clear_selection)
        — Description
    -   [newt\_listbox\_clear](/ref/newt.html#newt_listbox_clear) —
        Description
    -   [newt\_listbox\_delete\_entry](/ref/newt.html#newt_listbox_delete_entry)
        — Description
    -   [newt\_listbox\_get\_current](/ref/newt.html#newt_listbox_get_current)
        — Description
    -   [newt\_listbox\_get\_selection](/ref/newt.html#newt_listbox_get_selection)
        — Description
    -   [newt\_listbox\_insert\_entry](/ref/newt.html#newt_listbox_insert_entry)
        — Description
    -   [newt\_listbox\_item\_count](/ref/newt.html#newt_listbox_item_count)
        — Description
    -   [newt\_listbox\_select\_item](/ref/newt.html#newt_listbox_select_item)
        — Description
    -   [newt\_listbox\_set\_current\_by\_key](/ref/newt.html#newt_listbox_set_current_by_key)
        — Description
    -   [newt\_listbox\_set\_current](/ref/newt.html#newt_listbox_set_current)
        — Description
    -   [newt\_listbox\_set\_data](/ref/newt.html#newt_listbox_set_data)
        — Description
    -   [newt\_listbox\_set\_entry](/ref/newt.html#newt_listbox_set_entry)
        — Description
    -   [newt\_listbox\_set\_width](/ref/newt.html#newt_listbox_set_width)
        — Description
    -   [newt\_listbox](/ref/newt.html#newt_listbox) — Description
    -   [newt\_listitem\_get\_data](/ref/newt.html#newt_listitem_get_data)
        — Description
    -   [newt\_listitem\_set](/ref/newt.html#newt_listitem_set) —
        Description
    -   [newt\_listitem](/ref/newt.html#newt_listitem) — Description
    -   [newt\_open\_window](/ref/newt.html#newt_open_window) — Open a
        window of the specified size and position
    -   [newt\_pop\_help\_line](/ref/newt.html#newt_pop_help_line) —
        Replaces the current help line with the one from the stack
    -   [newt\_pop\_window](/ref/newt.html#newt_pop_window) — Removes
        the top window from the display
    -   [newt\_push\_help\_line](/ref/newt.html#newt_push_help_line) —
        Saves the current help line on a stack, and displays the new
        line
    -   [newt\_radio\_get\_current](/ref/newt.html#newt_radio_get_current)
        — Description
    -   [newt\_radiobutton](/ref/newt.html#newt_radiobutton) —
        Description
    -   [newt\_redraw\_help\_line](/ref/newt.html#newt_redraw_help_line)
        — Description
    -   [newt\_reflow\_text](/ref/newt.html#newt_reflow_text) —
        Description
    -   [newt\_refresh](/ref/newt.html#newt_refresh) — Updates modified
        portions of the screen
    -   [newt\_resize\_screen](/ref/newt.html#newt_resize_screen) —
        Description
    -   [newt\_resume](/ref/newt.html#newt_resume) — Resume using the
        newt interface after calling newt\_suspend
    -   [newt\_run\_form](/ref/newt.html#newt_run_form) — Runs a form
    -   [newt\_scale\_set](/ref/newt.html#newt_scale_set) — Description
    -   [newt\_scale](/ref/newt.html#newt_scale) — Description
    -   [newt\_scrollbar\_set](/ref/newt.html#newt_scrollbar_set) —
        Description
    -   [newt\_set\_help\_callback](/ref/newt.html#newt_set_help_callback)
        — Description
    -   [newt\_set\_suspend\_callback](/ref/newt.html#newt_set_suspend_callback)
        — Set a callback function which gets invoked when user presses
        the suspend key
    -   [newt\_suspend](/ref/newt.html#newt_suspend) — Tells newt to
        return the terminal to its initial state
    -   [newt\_textbox\_get\_num\_lines](/ref/newt.html#newt_textbox_get_num_lines)
        — Description
    -   [newt\_textbox\_reflowed](/ref/newt.html#newt_textbox_reflowed)
        — Description
    -   [newt\_textbox\_set\_height](/ref/newt.html#newt_textbox_set_height)
        — Description
    -   [newt\_textbox\_set\_text](/ref/newt.html#newt_textbox_set_text)
        — Description
    -   [newt\_textbox](/ref/newt.html#newt_textbox) — Description
    -   [newt\_vertical\_scrollbar](/ref/newt.html#newt_vertical_scrollbar)
        — Description
    -   [newt\_wait\_for\_key](/ref/newt.html#newt_wait_for_key) —
        Doesn't return until a key has been pressed
    -   [newt\_win\_choice](/ref/newt.html#newt_win_choice) —
        Description
    -   [newt\_win\_entries](/ref/newt.html#newt_win_entries) —
        Description
    -   [newt\_win\_menu](/ref/newt.html#newt_win_menu) — Description
    -   [newt\_win\_message](/ref/newt.html#newt_win_message) —
        Description
    -   [newt\_win\_messagev](/ref/newt.html#newt_win_messagev) —
        Description
    -   [newt\_win\_ternary](/ref/newt.html#newt_win_ternary) —
        Description
