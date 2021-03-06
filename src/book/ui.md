UI
==

**Table of Contents**

-   [Introduction](/intro/ui.html)
-   [Installing/Configuring](/ui/setup.html)
    -   [Requirements](/ui/setup.html#Requirements)
    -   [Installation](/ui/setup.html#Installation)
-   [UI\\Point](/class/ui-point.html) — Represents a position (x,y)
    -   [UI\\Point::at](/class/ui-point.html#UI\Point::at) — Size
        Coercion
    -   [UI\\Point::\_\_construct](/class/ui-point.html#UI\Point::__construct)
        — Construct a new Point
    -   [UI\\Point::getX](/class/ui-point.html#UI\Point::getX) —
        Retrieves X
    -   [UI\\Point::getY](/class/ui-point.html#UI\Point::getY) —
        Retrieves Y
    -   [UI\\Point::setX](/class/ui-point.html#UI\Point::setX) — Set X
    -   [UI\\Point::setY](/class/ui-point.html#UI\Point::setY) — Set Y
-   [UI\\Size](/class/ui-size.html) — Represents dimenstions (width,
    height)
    -   [UI\\Size::\_\_construct](/class/ui-size.html#UI\Size::__construct)
        — Construct a new Size
    -   [UI\\Size::getHeight](/class/ui-size.html#UI\Size::getHeight) —
        Retrieves Height
    -   [UI\\Size::getWidth](/class/ui-size.html#UI\Size::getWidth) —
        Retrives Width
    -   [UI\\Size::of](/class/ui-size.html#UI\Size::of) — Point Coercion
    -   [UI\\Size::setHeight](/class/ui-size.html#UI\Size::setHeight) —
        Set Height
    -   [UI\\Size::setWidth](/class/ui-size.html#UI\Size::setWidth) —
        Set Width
-   [UI\\Window](/class/ui-window.html) — Window
    -   [UI\\Window::add](/class/ui-window.html#UI\Window::add) — Add a
        Control
    -   [UI\\Window::\_\_construct](/class/ui-window.html#UI\Window::__construct)
        — Construct a new Window
    -   [UI\\Window::error](/class/ui-window.html#UI\Window::error) —
        Show Error Box
    -   [UI\\Window::getSize](/class/ui-window.html#UI\Window::getSize)
        — Get Window Size
    -   [UI\\Window::getTitle](/class/ui-window.html#UI\Window::getTitle)
        — Get Title
    -   [UI\\Window::hasBorders](/class/ui-window.html#UI\Window::hasBorders)
        — Border Detection
    -   [UI\\Window::hasMargin](/class/ui-window.html#UI\Window::hasMargin)
        — Margin Detection
    -   [UI\\Window::isFullScreen](/class/ui-window.html#UI\Window::isFullScreen)
        — Full Screen Detection
    -   [UI\\Window::msg](/class/ui-window.html#UI\Window::msg) — Show
        Message Box
    -   [UI\\Window::onClosing](/class/ui-window.html#UI\Window::onClosing)
        — Closing Callback
    -   [UI\\Window::open](/class/ui-window.html#UI\Window::open) — Open
        Dialog
    -   [UI\\Window::save](/class/ui-window.html#UI\Window::save) — Save
        Dialog
    -   [UI\\Window::setBorders](/class/ui-window.html#UI\Window::setBorders)
        — Border Use
    -   [UI\\Window::setFullScreen](/class/ui-window.html#UI\Window::setFullScreen)
        — Full Screen Use
    -   [UI\\Window::setMargin](/class/ui-window.html#UI\Window::setMargin)
        — Margin Use
    -   [UI\\Window::setSize](/class/ui-window.html#UI\Window::setSize)
        — Set Size
    -   [UI\\Window::setTitle](/class/ui-window.html#UI\Window::setTitle)
        — Window Title
-   [UI\\Control](/class/ui-control.html) — Control
    -   [UI\\Control::destroy](/class/ui-control.html#UI\Control::destroy)
        — Destroy Control
    -   [UI\\Control::disable](/class/ui-control.html#UI\Control::disable)
        — Disable Control
    -   [UI\\Control::enable](/class/ui-control.html#UI\Control::enable)
        — Enable Control
    -   [UI\\Control::getParent](/class/ui-control.html#UI\Control::getParent)
        — Get Parent Control
    -   [UI\\Control::getTopLevel](/class/ui-control.html#UI\Control::getTopLevel)
        — Get Top Level
    -   [UI\\Control::hide](/class/ui-control.html#UI\Control::hide) —
        Hide Control
    -   [UI\\Control::isEnabled](/class/ui-control.html#UI\Control::isEnabled)
        — Determine if Control is enabled
    -   [UI\\Control::isVisible](/class/ui-control.html#UI\Control::isVisible)
        — Determine if Control is visible
    -   [UI\\Control::setParent](/class/ui-control.html#UI\Control::setParent)
        — Set Parent Control
    -   [UI\\Control::show](/class/ui-control.html#UI\Control::show) —
        Control Show
-   [UI\\Menu](/class/ui-menu.html) — Menu
    -   [UI\\Menu::append](/class/ui-menu.html#UI\Menu::append) — Append
        Menu Item
    -   [UI\\Menu::appendAbout](/class/ui-menu.html#UI\Menu::appendAbout)
        — Append About Menu Item
    -   [UI\\Menu::appendCheck](/class/ui-menu.html#UI\Menu::appendCheck)
        — Append Checkable Menu Item
    -   [UI\\Menu::appendPreferences](/class/ui-menu.html#UI\Menu::appendPreferences)
        — Append Preferences Menu Item
    -   [UI\\Menu::appendQuit](/class/ui-menu.html#UI\Menu::appendQuit)
        — Append Quit Menu Item
    -   [UI\\Menu::appendSeparator](/class/ui-menu.html#UI\Menu::appendSeparator)
        — Append Menu Item Separator
    -   [UI\\Menu::\_\_construct](/class/ui-menu.html#UI\Menu::__construct)
        — Construct a new Menu
-   [UI\\MenuItem](/class/ui-menuitem.html) — Menu Item
    -   [UI\\MenuItem::disable](/class/ui-menuitem.html#UI\MenuItem::disable)
        — Disable Menu Item
    -   [UI\\MenuItem::enable](/class/ui-menuitem.html#UI\MenuItem::enable)
        — Enable Menu Item
    -   [UI\\MenuItem::isChecked](/class/ui-menuitem.html#UI\MenuItem::isChecked)
        — Detect Checked
    -   [UI\\MenuItem::onClick](/class/ui-menuitem.html#UI\MenuItem::onClick)
        — On Click Callback
    -   [UI\\MenuItem::setChecked](/class/ui-menuitem.html#UI\MenuItem::setChecked)
        — Set Checked
-   [UI\\Area](/class/ui-area.html) — Area
    -   [UI\\Area::onDraw](/class/ui-area.html#UI\Area::onDraw) — Draw
        Callback
    -   [UI\\Area::onKey](/class/ui-area.html#UI\Area::onKey) — Key
        Callback
    -   [UI\\Area::onMouse](/class/ui-area.html#UI\Area::onMouse) —
        Mouse Callback
    -   [UI\\Area::redraw](/class/ui-area.html#UI\Area::redraw) — Redraw
        Area
    -   [UI\\Area::scrollTo](/class/ui-area.html#UI\Area::scrollTo) —
        Area Scroll
    -   [UI\\Area::setSize](/class/ui-area.html#UI\Area::setSize) — Set
        Size
-   [UI\\Executor](/class/ui-executor.html) — Execution Scheduler
    -   [UI\\Executor::\_\_construct](/class/ui-executor.html#UI\Executor::__construct)
        — Construct a new Executor
    -   [UI\\Executor::kill](/class/ui-executor.html#UI\Executor::kill)
        — Stop Executor
    -   [UI\\Executor::onExecute](/class/ui-executor.html#UI\Executor::onExecute)
        — Execution Callback
    -   [UI\\Executor::setInterval](/class/ui-executor.html#UI\Executor::setInterval)
        — Interval Manipulation
-   [UI\\Controls\\Tab](/class/ui-controls-tab.html) — Tab Control
    -   [UI\\Controls\\Tab::append](/class/ui-controls-tab.html#UI\Controls\Tab::append)
        — Append Page
    -   [UI\\Controls\\Tab::delete](/class/ui-controls-tab.html#UI\Controls\Tab::delete)
        — Delete Page
    -   [UI\\Controls\\Tab::hasMargin](/class/ui-controls-tab.html#UI\Controls\Tab::hasMargin)
        — Margin Detection
    -   [UI\\Controls\\Tab::insertAt](/class/ui-controls-tab.html#UI\Controls\Tab::insertAt)
        — Insert Page
    -   [UI\\Controls\\Tab::pages](/class/ui-controls-tab.html#UI\Controls\Tab::pages)
        — Page Count
    -   [UI\\Controls\\Tab::setMargin](/class/ui-controls-tab.html#UI\Controls\Tab::setMargin)
        — Set Margin
-   [UI\\Controls\\Check](/class/ui-controls-check.html) — Check Control
    -   [UI\\Controls\\Check::\_\_construct](/class/ui-controls-check.html#UI\Controls\Check::__construct)
        — Construct a new Check
    -   [UI\\Controls\\Check::getText](/class/ui-controls-check.html#UI\Controls\Check::getText)
        — Get Text
    -   [UI\\Controls\\Check::isChecked](/class/ui-controls-check.html#UI\Controls\Check::isChecked)
        — Checked Detection
    -   [UI\\Controls\\Check::onToggle](/class/ui-controls-check.html#UI\Controls\Check::onToggle)
        — Toggle Callback
    -   [UI\\Controls\\Check::setChecked](/class/ui-controls-check.html#UI\Controls\Check::setChecked)
        — Set Checked
    -   [UI\\Controls\\Check::setText](/class/ui-controls-check.html#UI\Controls\Check::setText)
        — Set Text
-   [UI\\Controls\\Button](/class/ui-controls-button.html) — Button
    Control
    -   [UI\\Controls\\Button::\_\_construct](/class/ui-controls-button.html#UI\Controls\Button::__construct)
        — Construct a new Button
    -   [UI\\Controls\\Button::getText](/class/ui-controls-button.html#UI\Controls\Button::getText)
        — Get Text
    -   [UI\\Controls\\Button::onClick](/class/ui-controls-button.html#UI\Controls\Button::onClick)
        — Click Handler
    -   [UI\\Controls\\Button::setText](/class/ui-controls-button.html#UI\Controls\Button::setText)
        — Set Text
-   [UI\\Controls\\ColorButton](/class/ui-controls-colorbutton.html) —
    ColorButton Control
    -   [UI\\Controls\\ColorButton::getColor](/class/ui-controls-colorbutton.html#UI\Controls\ColorButton::getColor)
        — Get Color
    -   [UI\\Controls\\ColorButton::onChange](/class/ui-controls-colorbutton.html#UI\Controls\ColorButton::onChange)
        — Change Handler
    -   [UI\\Controls\\ColorButton::setColor](/class/ui-controls-colorbutton.html#UI\Controls\ColorButton::setColor)
        — Set Color
-   [UI\\Controls\\Label](/class/ui-controls-label.html) — Label Control
    -   [UI\\Controls\\Label::\_\_construct](/class/ui-controls-label.html#UI\Controls\Label::__construct)
        — Construct a new Label
    -   [UI\\Controls\\Label::getText](/class/ui-controls-label.html#UI\Controls\Label::getText)
        — Get Text
    -   [UI\\Controls\\Label::setText](/class/ui-controls-label.html#UI\Controls\Label::setText)
        — Set Text
-   [UI\\Controls\\Entry](/class/ui-controls-entry.html) — Entry Control
    -   [UI\\Controls\\Entry::\_\_construct](/class/ui-controls-entry.html#UI\Controls\Entry::__construct)
        — Construct a new Entry
    -   [UI\\Controls\\Entry::getText](/class/ui-controls-entry.html#UI\Controls\Entry::getText)
        — Get Text
    -   [UI\\Controls\\Entry::isReadOnly](/class/ui-controls-entry.html#UI\Controls\Entry::isReadOnly)
        — Detect Read Only
    -   [UI\\Controls\\Entry::onChange](/class/ui-controls-entry.html#UI\Controls\Entry::onChange)
        — Change Handler
    -   [UI\\Controls\\Entry::setReadOnly](/class/ui-controls-entry.html#UI\Controls\Entry::setReadOnly)
        — Set Read Only
    -   [UI\\Controls\\Entry::setText](/class/ui-controls-entry.html#UI\Controls\Entry::setText)
        — Set Text
-   [UI\\Controls\\MultilineEntry](/class/ui-controls-multilineentry.html)
    — MultilineEntry Control
    -   [UI\\Controls\\MultilineEntry::append](/class/ui-controls-multilineentry.html#UI\Controls\MultilineEntry::append)
        — Append Text
    -   [UI\\Controls\\MultilineEntry::\_\_construct](/class/ui-controls-multilineentry.html#UI\Controls\MultilineEntry::__construct)
        — Construct a new Multiline Entry
    -   [UI\\Controls\\MultilineEntry::getText](/class/ui-controls-multilineentry.html#UI\Controls\MultilineEntry::getText)
        — Get Text
    -   [UI\\Controls\\MultilineEntry::isReadOnly](/class/ui-controls-multilineentry.html#UI\Controls\MultilineEntry::isReadOnly)
        — Read Only Detection
    -   [UI\\Controls\\MultilineEntry::onChange](/class/ui-controls-multilineentry.html#UI\Controls\MultilineEntry::onChange)
        — Change Handler
    -   [UI\\Controls\\MultilineEntry::setReadOnly](/class/ui-controls-multilineentry.html#UI\Controls\MultilineEntry::setReadOnly)
        — Set Read Only
    -   [UI\\Controls\\MultilineEntry::setText](/class/ui-controls-multilineentry.html#UI\Controls\MultilineEntry::setText)
        — Set Text
-   [UI\\Controls\\Spin](/class/ui-controls-spin.html) — Spin Control
    -   [UI\\Controls\\Spin::\_\_construct](/class/ui-controls-spin.html#UI\Controls\Spin::__construct)
        — Construct a new Spin
    -   [UI\\Controls\\Spin::getValue](/class/ui-controls-spin.html#UI\Controls\Spin::getValue)
        — Get Value
    -   [UI\\Controls\\Spin::onChange](/class/ui-controls-spin.html#UI\Controls\Spin::onChange)
        — Change Handler
    -   [UI\\Controls\\Spin::setValue](/class/ui-controls-spin.html#UI\Controls\Spin::setValue)
        — Set Value
-   [UI\\Controls\\Slider](/class/ui-controls-slider.html) — Slider
    Control
    -   [UI\\Controls\\Slider::\_\_construct](/class/ui-controls-slider.html#UI\Controls\Slider::__construct)
        — Construct a new Slider
    -   [UI\\Controls\\Slider::getValue](/class/ui-controls-slider.html#UI\Controls\Slider::getValue)
        — Get Value
    -   [UI\\Controls\\Slider::onChange](/class/ui-controls-slider.html#UI\Controls\Slider::onChange)
        — Change Handler
    -   [UI\\Controls\\Slider::setValue](/class/ui-controls-slider.html#UI\Controls\Slider::setValue)
        — Set Value
-   [UI\\Controls\\Progress](/class/ui-controls-progress.html) —
    Progress Control
    -   [UI\\Controls\\Progress::getValue](/class/ui-controls-progress.html#UI\Controls\Progress::getValue)
        — Get Value
    -   [UI\\Controls\\Progress::setValue](/class/ui-controls-progress.html#UI\Controls\Progress::setValue)
        — Set Value
-   [UI\\Controls\\Separator](/class/ui-controls-separator.html) —
    Control Separator
    -   [UI\\Controls\\Separator::\_\_construct](/class/ui-controls-separator.html#UI\Controls\Separator::__construct)
        — Construct a new Separator
-   [UI\\Controls\\Combo](/class/ui-controls-combo.html) — Combo Control
    -   [UI\\Controls\\Combo::append](/class/ui-controls-combo.html#UI\Controls\Combo::append)
        — Append Option
    -   [UI\\Controls\\Combo::getSelected](/class/ui-controls-combo.html#UI\Controls\Combo::getSelected)
        — Get Selected Option
    -   [UI\\Controls\\Combo::onSelected](/class/ui-controls-combo.html#UI\Controls\Combo::onSelected)
        — Selected Handler
    -   [UI\\Controls\\Combo::setSelected](/class/ui-controls-combo.html#UI\Controls\Combo::setSelected)
        — Set Selected Option
-   [UI\\Controls\\EditableCombo](/class/ui-controls-editablecombo.html)
    — EdiableCombo Control
    -   [UI\\Controls\\EditableCombo::append](/class/ui-controls-editablecombo.html#UI\Controls\EditableCombo::append)
        — Append Option
    -   [UI\\Controls\\EditableCombo::getText](/class/ui-controls-editablecombo.html#UI\Controls\EditableCombo::getText)
        — Get Text
    -   [UI\\Controls\\EditableCombo::onChange](/class/ui-controls-editablecombo.html#UI\Controls\EditableCombo::onChange)
        — Change Handler
    -   [UI\\Controls\\EditableCombo::setText](/class/ui-controls-editablecombo.html#UI\Controls\EditableCombo::setText)
        — Set Text
-   [UI\\Controls\\Radio](/class/ui-controls-radio.html) — Radio Control
    -   [UI\\Controls\\Radio::append](/class/ui-controls-radio.html#UI\Controls\Radio::append)
        — Append Option
    -   [UI\\Controls\\Radio::getSelected](/class/ui-controls-radio.html#UI\Controls\Radio::getSelected)
        — Get Selected Option
    -   [UI\\Controls\\Radio::onSelected](/class/ui-controls-radio.html#UI\Controls\Radio::onSelected)
        — Selected Handler
    -   [UI\\Controls\\Radio::setSelected](/class/ui-controls-radio.html#UI\Controls\Radio::setSelected)
        — Set Selected Option
-   [UI\\Controls\\Picker](/class/ui-controls-picker.html) — Picker
    Control
    -   [UI\\Controls\\Picker::\_\_construct](/class/ui-controls-picker.html#UI\Controls\Picker::__construct)
        — Construct a new Picker
-   [UI\\Controls\\Form](/class/ui-controls-form.html) — Control Form
    (Arrangement)
    -   [UI\\Controls\\Form::append](/class/ui-controls-form.html#UI\Controls\Form::append)
        — Append Control
    -   [UI\\Controls\\Form::delete](/class/ui-controls-form.html#UI\Controls\Form::delete)
        — Delete Control
    -   [UI\\Controls\\Form::isPadded](/class/ui-controls-form.html#UI\Controls\Form::isPadded)
        — Padding Detection
    -   [UI\\Controls\\Form::setPadded](/class/ui-controls-form.html#UI\Controls\Form::setPadded)
        — Set Padding
-   [UI\\Controls\\Grid](/class/ui-controls-grid.html) — Control Grid
    (Arrangement)
    -   [UI\\Controls\\Grid::append](/class/ui-controls-grid.html#UI\Controls\Grid::append)
        — Append Control
    -   [UI\\Controls\\Grid::isPadded](/class/ui-controls-grid.html#UI\Controls\Grid::isPadded)
        — Padding Detection
    -   [UI\\Controls\\Grid::setPadded](/class/ui-controls-grid.html#UI\Controls\Grid::setPadded)
        — Set Padding
-   [UI\\Controls\\Group](/class/ui-controls-group.html) — Control Group
    (Arrangement)
    -   [UI\\Controls\\Group::append](/class/ui-controls-group.html#UI\Controls\Group::append)
        — Append Control
    -   [UI\\Controls\\Group::\_\_construct](/class/ui-controls-group.html#UI\Controls\Group::__construct)
        — Construct a new Group
    -   [UI\\Controls\\Group::getTitle](/class/ui-controls-group.html#UI\Controls\Group::getTitle)
        — Get Title
    -   [UI\\Controls\\Group::hasMargin](/class/ui-controls-group.html#UI\Controls\Group::hasMargin)
        — Margin Detection
    -   [UI\\Controls\\Group::setMargin](/class/ui-controls-group.html#UI\Controls\Group::setMargin)
        — Set Margin
    -   [UI\\Controls\\Group::setTitle](/class/ui-controls-group.html#UI\Controls\Group::setTitle)
        — Set Title
-   [UI\\Controls\\Box](/class/ui-controls-box.html) — Control Box
    (Arrangement)
    -   [UI\\Controls\\Box::append](/class/ui-controls-box.html#UI\Controls\Box::append)
        — Append Control
    -   [UI\\Controls\\Box::\_\_construct](/class/ui-controls-box.html#UI\Controls\Box::__construct)
        — Construct a new Box
    -   [UI\\Controls\\Box::delete](/class/ui-controls-box.html#UI\Controls\Box::delete)
        — Delete Control
    -   [UI\\Controls\\Box::getOrientation](/class/ui-controls-box.html#UI\Controls\Box::getOrientation)
        — Get Orientation
    -   [UI\\Controls\\Box::isPadded](/class/ui-controls-box.html#UI\Controls\Box::isPadded)
        — Padding Detection
    -   [UI\\Controls\\Box::setPadded](/class/ui-controls-box.html#UI\Controls\Box::setPadded)
        — Set Padding
-   [UI\\Draw\\Pen](/class/ui-draw-pen.html) — Draw Pen
    -   [UI\\Draw\\Pen::clip](/class/ui-draw-pen.html#UI\Draw\Pen::clip)
        — Clip a Path
    -   [UI\\Draw\\Pen::fill](/class/ui-draw-pen.html#UI\Draw\Pen::fill)
        — Fill a Path
    -   [UI\\Draw\\Pen::restore](/class/ui-draw-pen.html#UI\Draw\Pen::restore)
        — Restore
    -   [UI\\Draw\\Pen::save](/class/ui-draw-pen.html#UI\Draw\Pen::save)
        — Save
    -   [UI\\Draw\\Pen::stroke](/class/ui-draw-pen.html#UI\Draw\Pen::stroke)
        — Stroke a Path
    -   [UI\\Draw\\Pen::transform](/class/ui-draw-pen.html#UI\Draw\Pen::transform)
        — Matrix Transform
    -   [UI\\Draw\\Pen::write](/class/ui-draw-pen.html#UI\Draw\Pen::write)
        — Draw Text at Point
-   [UI\\Draw\\Path](/class/ui-draw-path.html) — Draw Path
    -   [UI\\Draw\\Path::addRectangle](/class/ui-draw-path.html#UI\Draw\Path::addRectangle)
        — Draw a Rectangle
    -   [UI\\Draw\\Path::arcTo](/class/ui-draw-path.html#UI\Draw\Path::arcTo)
        — Draw an Arc
    -   [UI\\Draw\\Path::bezierTo](/class/ui-draw-path.html#UI\Draw\Path::bezierTo)
        — Draw Bezier Curve
    -   [UI\\Draw\\Path::closeFigure](/class/ui-draw-path.html#UI\Draw\Path::closeFigure)
        — Close Figure
    -   [UI\\Draw\\Path::\_\_construct](/class/ui-draw-path.html#UI\Draw\Path::__construct)
        — Construct a new Path
    -   [UI\\Draw\\Path::end](/class/ui-draw-path.html#UI\Draw\Path::end)
        — Finalize Path
    -   [UI\\Draw\\Path::lineTo](/class/ui-draw-path.html#UI\Draw\Path::lineTo)
        — Draw a Line
    -   [UI\\Draw\\Path::newFigure](/class/ui-draw-path.html#UI\Draw\Path::newFigure)
        — Draw Figure
    -   [UI\\Draw\\Path::newFigureWithArc](/class/ui-draw-path.html#UI\Draw\Path::newFigureWithArc)
        — Draw Figure with Arc
-   [UI\\Draw\\Matrix](/class/ui-draw-matrix.html) — Draw Matrix
    -   [UI\\Draw\\Matrix::invert](/class/ui-draw-matrix.html#UI\Draw\Matrix::invert)
        — Invert Matrix
    -   [UI\\Draw\\Matrix::isInvertible](/class/ui-draw-matrix.html#UI\Draw\Matrix::isInvertible)
        — Invertible Detection
    -   [UI\\Draw\\Matrix::multiply](/class/ui-draw-matrix.html#UI\Draw\Matrix::multiply)
        — Multiply Matrix
    -   [UI\\Draw\\Matrix::rotate](/class/ui-draw-matrix.html#UI\Draw\Matrix::rotate)
        — Rotate Matrix
    -   [UI\\Draw\\Matrix::scale](/class/ui-draw-matrix.html#UI\Draw\Matrix::scale)
        — Scale Matrix
    -   [UI\\Draw\\Matrix::skew](/class/ui-draw-matrix.html#UI\Draw\Matrix::skew)
        — Skew Matrix
    -   [UI\\Draw\\Matrix::translate](/class/ui-draw-matrix.html#UI\Draw\Matrix::translate)
        — Translate Matrix
-   [UI\\Draw\\Color](/class/ui-draw-color.html) — Color Representation
    -   [UI\\Draw\\Color::\_\_construct](/class/ui-draw-color.html#UI\Draw\Color::__construct)
        — Construct new Color
    -   [UI\\Draw\\Color::getChannel](/class/ui-draw-color.html#UI\Draw\Color::getChannel)
        — Color Manipulation
    -   [UI\\Draw\\Color::setChannel](/class/ui-draw-color.html#UI\Draw\Color::setChannel)
        — Color Manipulation
-   [UI\\Draw\\Stroke](/class/ui-draw-stroke.html) — Draw Stroke
    -   [UI\\Draw\\Stroke::\_\_construct](/class/ui-draw-stroke.html#UI\Draw\Stroke::__construct)
        — Construct a new Stroke
    -   [UI\\Draw\\Stroke::getCap](/class/ui-draw-stroke.html#UI\Draw\Stroke::getCap)
        — Get Line Cap
    -   [UI\\Draw\\Stroke::getJoin](/class/ui-draw-stroke.html#UI\Draw\Stroke::getJoin)
        — Get Line Join
    -   [UI\\Draw\\Stroke::getMiterLimit](/class/ui-draw-stroke.html#UI\Draw\Stroke::getMiterLimit)
        — Get Miter Limit
    -   [UI\\Draw\\Stroke::getThickness](/class/ui-draw-stroke.html#UI\Draw\Stroke::getThickness)
        — Get Thickness
    -   [UI\\Draw\\Stroke::setCap](/class/ui-draw-stroke.html#UI\Draw\Stroke::setCap)
        — Set Line Cap
    -   [UI\\Draw\\Stroke::setJoin](/class/ui-draw-stroke.html#UI\Draw\Stroke::setJoin)
        — Set Line Join
    -   [UI\\Draw\\Stroke::setMiterLimit](/class/ui-draw-stroke.html#UI\Draw\Stroke::setMiterLimit)
        — Set Miter Limit
    -   [UI\\Draw\\Stroke::setThickness](/class/ui-draw-stroke.html#UI\Draw\Stroke::setThickness)
        — Set Thickness
-   [UI\\Draw\\Brush](/class/ui-draw-brush.html) — Brushes
    -   [UI\\Draw\\Brush::\_\_construct](/class/ui-draw-brush.html#UI\Draw\Brush::__construct)
        — Construct a new Brush
    -   [UI\\Draw\\Brush::getColor](/class/ui-draw-brush.html#UI\Draw\Brush::getColor)
        — Get Color
    -   [UI\\Draw\\Brush::setColor](/class/ui-draw-brush.html#UI\Draw\Brush::setColor)
        — Set Color
-   [UI\\Draw\\Brush\\Gradient](/class/ui-draw-brush-gradient.html) —
    Gradient Brushes
    -   [UI\\Draw\\Brush\\Gradient::addStop](/class/ui-draw-brush-gradient.html#UI\Draw\Brush\Gradient::addStop)
        — Stop Manipulation
    -   [UI\\Draw\\Brush\\Gradient::delStop](/class/ui-draw-brush-gradient.html#UI\Draw\Brush\Gradient::delStop)
        — Stop Manipulation
    -   [UI\\Draw\\Brush\\Gradient::setStop](/class/ui-draw-brush-gradient.html#UI\Draw\Brush\Gradient::setStop)
        — Stop Manipulation
-   [UI\\Draw\\Brush\\LinearGradient](/class/ui-draw-brush-lineargradient.html)
    — Linear Gradient
    -   [UI\\Draw\\Brush\\LinearGradient::\_\_construct](/class/ui-draw-brush-lineargradient.html#UI\Draw\Brush\LinearGradient::__construct)
        — Construct a Linear Gradient
-   [UI\\Draw\\Brush\\RadialGradient](/class/ui-draw-brush-radialgradient.html)
    — Radial Gradient
    -   [UI\\Draw\\Brush\\RadialGradient::\_\_construct](/class/ui-draw-brush-radialgradient.html#UI\Draw\Brush\RadialGradient::__construct)
        — Construct a new Radial Gradient
-   [UI\\Draw\\Text\\Layout](/class/ui-draw-text-layout.html) —
    Represents Text Layout
    -   [UI\\Draw\\Text\\Layout::\_\_construct](/class/ui-draw-text-layout.html#UI\Draw\Text\Layout::__construct)
        — Construct a new Text Layout
    -   [UI\\Draw\\Text\\Layout::setColor](/class/ui-draw-text-layout.html#UI\Draw\Text\Layout::setColor)
        — Set Color
    -   [UI\\Draw\\Text\\Layout::setWidth](/class/ui-draw-text-layout.html#UI\Draw\Text\Layout::setWidth)
        — Set Width
-   [UI\\Draw\\Text\\Font](/class/ui-draw-text-font.html) — Represents a
    Font
    -   [UI\\Draw\\Text\\Font::\_\_construct](/class/ui-draw-text-font.html#UI\Draw\Text\Font::__construct)
        — Construct a new Font
    -   [UI\\Draw\\Text\\Font::getAscent](/class/ui-draw-text-font.html#UI\Draw\Text\Font::getAscent)
        — Font Metrics
    -   [UI\\Draw\\Text\\Font::getDescent](/class/ui-draw-text-font.html#UI\Draw\Text\Font::getDescent)
        — Font Metrics
    -   [UI\\Draw\\Text\\Font::getLeading](/class/ui-draw-text-font.html#UI\Draw\Text\Font::getLeading)
        — Font Metrics
    -   [UI\\Draw\\Text\\Font::getUnderlinePosition](/class/ui-draw-text-font.html#UI\Draw\Text\Font::getUnderlinePosition)
        — Font Metrics
    -   [UI\\Draw\\Text\\Font::getUnderlineThickness](/class/ui-draw-text-font.html#UI\Draw\Text\Font::getUnderlineThickness)
        — Font Metrics
-   [UI\\Draw\\Text\\Font\\Descriptor](/class/ui-draw-text-font-descriptor.html)
    — Font Descriptor
    -   [UI\\Draw\\Text\\Font\\Descriptor::\_\_construct](/class/ui-draw-text-font-descriptor.html#UI\Draw\Text\Font\Descriptor::__construct)
        — Construct a new Font Descriptor
    -   [UI\\Draw\\Text\\Font\\Descriptor::getFamily](/class/ui-draw-text-font-descriptor.html#UI\Draw\Text\Font\Descriptor::getFamily)
        — Get Font Family
    -   [UI\\Draw\\Text\\Font\\Descriptor::getItalic](/class/ui-draw-text-font-descriptor.html#UI\Draw\Text\Font\Descriptor::getItalic)
        — Style Detection
    -   [UI\\Draw\\Text\\Font\\Descriptor::getSize](/class/ui-draw-text-font-descriptor.html#UI\Draw\Text\Font\Descriptor::getSize)
        — Size Detection
    -   [UI\\Draw\\Text\\Font\\Descriptor::getStretch](/class/ui-draw-text-font-descriptor.html#UI\Draw\Text\Font\Descriptor::getStretch)
        — Style Detection
    -   [UI\\Draw\\Text\\Font\\Descriptor::getWeight](/class/ui-draw-text-font-descriptor.html#UI\Draw\Text\Font\Descriptor::getWeight)
        — Weight Detection
-   [UI Functions](/ref/ui.html)
    -   [UI\\Draw\\Text\\Font\\fontFamilies](/ref/ui.html#UI\Draw\Text\Font\fontFamilies)
        — Retrieve Font Families
    -   [UI\\quit](/ref/ui.html#UI\quit) — Quit UI Loop
    -   [UI\\run](/ref/ui.html#UI\run) — Enter UI Loop
-   [UI\\Draw\\Text\\Font\\Weight](/class/ui-draw-text-font-weight.html)
    — Font Weight Settings
-   [UI\\Draw\\Text\\Font\\Italic](/class/ui-draw-text-font-italic.html)
    — Italic Font Settings
-   [UI\\Draw\\Text\\Font\\Stretch](/class/ui-draw-text-font-stretch.html)
    — Font Stretch Settings
-   [UI\\Draw\\Line\\Cap](/class/ui-draw-line-cap.html) — Line Cap
    Settings
-   [UI\\Draw\\Line\\Join](/class/ui-draw-line-join.html) — Line Join
    Settings
-   [UI\\Key](/class/ui-key.html) — Key Identifiers
-   [UI\\Exception\\InvalidArgumentException](/class/ui-exception-invalidargumentexception.html)
    — InvalidArgumentException
-   [UI\\Exception\\RuntimeException](/class/ui-exception-runtimeexception.html)
    — RuntimeException

Introduction
------------

Points are used throughout UI to represent co-ordinates on a screen,
control, or area.

Class synopsis
--------------

**UI\\Point**

<span class="ooclass"> <span class="modifier">final</span> class
**UI\\Point** </span> {

/\* Properties \*/

<span class="modifier">public</span> `$x` ;

<span class="modifier">public</span> `$y` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">UI\\Point</span> <span
class="methodname">at</span> ( <span class="methodparam"><span
class="type">float</span> `$point`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">UI\\Point</span> <span
class="methodname">at</span> ( <span class="methodparam"><span
class="type">UI\\Size</span> `$size`</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getX</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getY</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setX</span> ( <span class="methodparam"><span
class="type">float</span> `$point`</span> )

<span class="modifier">public</span> <span
class="methodname">setY</span> ( <span class="methodparam"><span
class="type">float</span> `$point`</span> )

}

Properties
----------

`x`  
Holds the X co-ordinate, can be read/written directly

`y`  
Holds the Y co-ordinate, can be read/written directly

UI\\Point::at
=============

Size Coercion

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">UI\\Point</span> <span
class="methodname">UI\\Point::at</span> ( <span
class="methodparam"><span class="type">float</span> `$point`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">UI\\Point</span> <span
class="methodname">UI\\Point::at</span> ( <span
class="methodparam"><span class="type">UI\\Size</span> `$size`</span> )

Shall return a UI\\Point object where x and y are equal to those
supplied, either in float or UI\\Size form

### Parameters

`point`  
The value for x and y

`size`  
The Size to convert

### Return Values

The resulting Point

UI\\Point::\_\_construct
========================

Construct a new Point

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Point::\_\_construct</span> ( <span
class="methodparam"><span class="type">float</span> `$x`</span> , <span
class="methodparam"><span class="type">float</span> `$y`</span> )

Construct a new Point using new co-ordinates

### Parameters

`x`  
The new X co-ordinate

`y`  
The new Y co-ordinate

UI\\Point::getX
===============

Retrieves X

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">UI\\Point::getX</span> ( <span
class="methodparam">void</span> )

Retrieves the X co-ordinate

### Parameters

This function has no parameters.

### Return Values

The current X co-ordinate

UI\\Point::getY
===============

Retrieves Y

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">UI\\Point::getY</span> ( <span
class="methodparam">void</span> )

Retrieves the Y co-ordinate

### Parameters

This function has no parameters.

### Return Values

The current Y co-ordinate

UI\\Point::setX
===============

Set X

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Point::setX</span> ( <span
class="methodparam"><span class="type">float</span> `$point`</span> )

Set the X co-ordinate

### Parameters

`point`  
The new X co-ordinate

### Return Values

UI\\Point::setY
===============

Set Y

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Point::setY</span> ( <span
class="methodparam"><span class="type">float</span> `$point`</span> )

Set the Y co-ordinate

### Parameters

`point`  
The new Y co-ordinate

### Return Values

Introduction
------------

Sizes are used throughout UI to represent the size of a screen, control,
or area.

Class synopsis
--------------

**UI\\Size**

<span class="ooclass"> <span class="modifier">final</span> class
**UI\\Size** </span> {

/\* Properties \*/

<span class="modifier">public</span> `$width` ;

<span class="modifier">public</span> `$height` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">float</span> `$width`</span> ,
<span class="methodparam"><span class="type">float</span>
`$height`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getHeight</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getWidth</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">UI\\Size</span> <span
class="methodname">of</span> ( <span class="methodparam"><span
class="type">float</span> `$size`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">UI\\Size</span> <span
class="methodname">of</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> )

<span class="modifier">public</span> <span
class="methodname">setHeight</span> ( <span class="methodparam"><span
class="type">float</span> `$size`</span> )

<span class="modifier">public</span> <span
class="methodname">setWidth</span> ( <span class="methodparam"><span
class="type">float</span> `$size`</span> )

}

Properties
----------

`width`  
Holds the width, can be read/written directly

`height`  
Holds the height, can be read/written directly

UI\\Size::\_\_construct
=======================

Construct a new Size

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Size::\_\_construct</span> ( <span
class="methodparam"><span class="type">float</span> `$width`</span> ,
<span class="methodparam"><span class="type">float</span>
`$height`</span> )

Construct a new Size using new width and height

### Parameters

`width`  
The new width

`height`  
The new height

UI\\Size::getHeight
===================

Retrieves Height

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">UI\\Size::getHeight</span> ( <span
class="methodparam">void</span> )

Retrieves the Height

### Parameters

This function has no parameters.

### Return Values

The current Height

UI\\Size::getWidth
==================

Retrives Width

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">UI\\Size::getWidth</span> ( <span
class="methodparam">void</span> )

Retrieves the Width

### Parameters

This function has no parameters.

### Return Values

The current Width

UI\\Size::of
============

Point Coercion

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">UI\\Size</span> <span
class="methodname">UI\\Size::of</span> ( <span class="methodparam"><span
class="type">float</span> `$size`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">UI\\Size</span> <span
class="methodname">UI\\Size::of</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> )

Shall return a UI\\Size object where width and height are equal to those
supplied, either in float or UI\\Point form

### Parameters

`size`  
The value for width and height

`point`  
The Point to convert

### Return Values

The resulting Size

UI\\Size::setHeight
===================

Set Height

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Size::setHeight</span> ( <span
class="methodparam"><span class="type">float</span> `$size`</span> )

Set new Height

### Parameters

`size`  
The new Height

### Return Values

UI\\Size::setWidth
==================

Set Width

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Size::setWidth</span> ( <span
class="methodparam"><span class="type">float</span> `$size`</span> )

Set new Width

### Parameters

`size`  
The new Width

### Return Values

Introduction
------------

Represents a UI Window

Class synopsis
--------------

**UI\\Window**

<span class="ooclass"> class **UI\\Window** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> `$controls` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> ,
<span class="methodparam"><span class="type">Size</span> `$size`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$menu`<span class="initializer"> = **`false`**</span></span> \] )

/\* Methods \*/

<span class="modifier">public</span> <span class="methodname">add</span>
( <span class="methodparam"><span class="type">UI\\Control</span>
`$control`</span> )

<span class="modifier">public</span> <span
class="methodname">error</span> ( <span class="methodparam"><span
class="type">string</span> `$title`</span> , <span
class="methodparam"><span class="type">string</span> `$msg`</span> )

<span class="modifier">public</span> <span class="type">UI\\Size</span>
<span class="methodname">getSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getTitle</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasBorders</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasMargin</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isFullScreen</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="methodname">msg</span>
( <span class="methodparam"><span class="type">string</span>
`$title`</span> , <span class="methodparam"><span
class="type">string</span> `$msg`</span> )

<span class="modifier">protected</span> <span class="type">int</span>
<span class="methodname">onClosing</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">open</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">save</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setBorders</span> ( <span class="methodparam"><span
class="type">bool</span> `$borders`</span> )

<span class="modifier">public</span> <span
class="methodname">setFullScreen</span> ( <span
class="methodparam"><span class="type">bool</span> `$full`</span> )

<span class="modifier">public</span> <span
class="methodname">setMargin</span> ( <span class="methodparam"><span
class="type">bool</span> `$margin`</span> )

<span class="modifier">public</span> <span
class="methodname">setSize</span> ( <span class="methodparam"><span
class="type">UI\\Size</span> `$size`</span> )

<span class="modifier">public</span> <span
class="methodname">setTitle</span> ( <span class="methodparam"><span
class="type">string</span> `$title`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`controls`  
Contains controls, should not be manipulated directly

UI\\Window::add
===============

Add a Control

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Window::add</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$control`</span> )

Shall add a Control to this Window

### Parameters

`control`  
The Control to add

### Return Values

UI\\Window::\_\_construct
=========================

Construct a new Window

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Window::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> ,
<span class="methodparam"><span class="type">Size</span> `$size`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$menu`<span class="initializer"> = **`false`**</span></span> \] )

Shall construct a new Window

### Parameters

`title`  
The title of the Window

`size`  
The size of the Window

`menu`  
Menu switch

UI\\Window::error
=================

Show Error Box

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Window::error</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> ,
<span class="methodparam"><span class="type">string</span> `$msg`</span>
)

Shall show an error box

### Parameters

`title`  
The title of the error box

`msg`  
The message for the error box

UI\\Window::getSize
===================

Get Window Size

### Description

<span class="modifier">public</span> <span class="type">UI\\Size</span>
<span class="methodname">UI\\Window::getSize</span> ( <span
class="methodparam">void</span> )

Shall return the size of this Window

### Parameters

This function has no parameters.

### Return Values

UI\\Window::getTitle
====================

Get Title

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">UI\\Window::getTitle</span> ( <span
class="methodparam">void</span> )

Shall retrieve the title of this Window

### Parameters

This function has no parameters.

### Return Values

UI\\Window::hasBorders
======================

Border Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Window::hasBorders</span> ( <span
class="methodparam">void</span> )

Shall detect if borders are used on this Window

### Parameters

This function has no parameters.

### Return Values

UI\\Window::hasMargin
=====================

Margin Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Window::hasMargin</span> ( <span
class="methodparam">void</span> )

Shall detect if margins are used on this Window

### Parameters

This function has no parameters.

### Return Values

UI\\Window::isFullScreen
========================

Full Screen Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Window::isFullScreen</span> ( <span
class="methodparam">void</span> )

Shall detect if this Window us using the whole screen

### Parameters

This function has no parameters.

### Return Values

UI\\Window::msg
===============

Show Message Box

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Window::msg</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> ,
<span class="methodparam"><span class="type">string</span> `$msg`</span>
)

Shall show a message box

### Parameters

`title`  
The title of the message box

`msg`  
The message

UI\\Window::onClosing
=====================

Closing Callback

### Description

<span class="modifier">protected</span> <span class="type">int</span>
<span class="methodname">UI\\Window::onClosing</span> ( <span
class="methodparam">void</span> )

Should gracefully destroy this Window

### Parameters

This function has no parameters.

### Return Values

UI\\Window::open
================

Open Dialog

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">UI\\Window::open</span> ( <span
class="methodparam">void</span> )

Shall show an open file dialog

### Parameters

This function has no parameters.

### Return Values

Returns the name of the file selected for opening

UI\\Window::save
================

Save Dialog

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">UI\\Window::save</span> ( <span
class="methodparam">void</span> )

Shall show a save dialog

### Parameters

This function has no parameters.

### Return Values

Returns the file name selecting for saving

UI\\Window::setBorders
======================

Border Use

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Window::setBorders</span> ( <span
class="methodparam"><span class="type">bool</span> `$borders`</span> )

Shall enable or disable the use of borders on this Window

### Parameters

`borders`  

UI\\Window::setFullScreen
=========================

Full Screen Use

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Window::setFullScreen</span> ( <span
class="methodparam"><span class="type">bool</span> `$full`</span> )

Shall enable or disable the use of the full screen for this Window

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`full`  

UI\\Window::setMargin
=====================

Margin Use

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Window::setMargin</span> ( <span
class="methodparam"><span class="type">bool</span> `$margin`</span> )

Shall enable or disable the use of margins for this Window

### Parameters

`margin`  

UI\\Window::setSize
===================

Set Size

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Window::setSize</span> ( <span
class="methodparam"><span class="type">UI\\Size</span> `$size`</span> )

Shall set the size of this Window

### Parameters

`size`  

### Return Values

UI\\Window::setTitle
====================

Window Title

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Window::setTitle</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> )

Shall set the title for this Window

### Parameters

`title`  
The new title

Introduction
------------

This is the closed base class for all UI Controls.

Class synopsis
--------------

**UI\\Control**

<span class="ooclass"> <span class="modifier">final</span> class
**UI\\Control** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">enable</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">hide</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setParent</span> ( <span class="methodparam"><span
class="type">UI\\Control</span> `$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">show</span> ( <span class="methodparam">void</span> )

}

UI\\Control::destroy
====================

Destroy Control

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

Shall destroy this Control

### Parameters

This function has no parameters.

### Return Values

UI\\Control::disable
====================

Disable Control

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

Shall disable this Control

### Parameters

This function has no parameters.

### Return Values

UI\\Control::enable
===================

Enable Control

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

Shall enable this Control

### Parameters

This function has no parameters.

### Return Values

UI\\Control::getParent
======================

Get Parent Control

### Description

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

Shall return the parent Control

### Parameters

This function has no parameters.

### Return Values

UI\\Control::getTopLevel
========================

Get Top Level

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

UI\\Control::hide
=================

Hide Control

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

Shall hide this Control

### Parameters

This function has no parameters.

### Return Values

UI\\Control::isEnabled
======================

Determine if Control is enabled

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

Shall detect if this Control is enabled

### Parameters

This function has no parameters.

### Return Values

UI\\Control::isVisible
======================

Determine if Control is visible

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

Shall detect if this Control is visible

### Parameters

This function has no parameters.

### Return Values

UI\\Control::setParent
======================

Set Parent Control

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

Shall set the parent Control of this Control

### Parameters

`parent`  
The parent Control

### Return Values

UI\\Control::show
=================

Control Show

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

Shall show this Control

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

Menus must be constructed before the first Window, and can be shown on
any Window

Class synopsis
--------------

**UI\\Menu**

<span class="ooclass"> class **UI\\Menu** </span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span
class="type">UI\\MenuItem</span> <span class="methodname">append</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$type`<span class="initializer"> =
UI\\MenuItem::class</span></span> \] )

<span class="modifier">public</span> <span
class="type">UI\\MenuItem</span> <span
class="methodname">appendAbout</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = UI\\MenuItem::class</span></span> \] )

<span class="modifier">public</span> <span
class="type">UI\\MenuItem</span> <span
class="methodname">appendCheck</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = UI\\MenuItem::class</span></span> \] )

<span class="modifier">public</span> <span
class="type">UI\\MenuItem</span> <span
class="methodname">appendPreferences</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = UI\\MenuItem::class</span></span> \] )

<span class="modifier">public</span> <span
class="type">UI\\MenuItem</span> <span
class="methodname">appendQuit</span> (\[ <span class="methodparam"><span
class="type">string</span> `$type`<span class="initializer"> =
UI\\MenuItem::class</span></span> \] )

<span class="modifier">public</span> <span
class="methodname">appendSeparator</span> ( <span
class="methodparam">void</span> )

}

UI\\Menu::append
================

Append Menu Item

### Description

<span class="modifier">public</span> <span
class="type">UI\\MenuItem</span> <span
class="methodname">UI\\Menu::append</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = UI\\MenuItem::class</span></span> \] )

Shall append a new Menu Item

### Parameters

`name`  
The name (text) for the new item

`type`  
The type for the new item

### Return Values

A constructed object of the given type

UI\\Menu::appendAbout
=====================

Append About Menu Item

### Description

<span class="modifier">public</span> <span
class="type">UI\\MenuItem</span> <span
class="methodname">UI\\Menu::appendAbout</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = UI\\MenuItem::class</span></span> \] )

Shall append an About menu item

### Parameters

`type`  
The type for the new item

### Return Values

A constructed About menu item of the given type

UI\\Menu::appendCheck
=====================

Append Checkable Menu Item

### Description

<span class="modifier">public</span> <span
class="type">UI\\MenuItem</span> <span
class="methodname">UI\\Menu::appendCheck</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = UI\\MenuItem::class</span></span> \] )

Shall append a checkable menu item

### Parameters

`name`  
The name (text) for the new item

`type`  
The type for the new item

### Return Values

A constructed checkable menu item of the given type

UI\\Menu::appendPreferences
===========================

Append Preferences Menu Item

### Description

<span class="modifier">public</span> <span
class="type">UI\\MenuItem</span> <span
class="methodname">UI\\Menu::appendPreferences</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = UI\\MenuItem::class</span></span> \] )

Shall append a Preferences menu item

### Parameters

`type`  
The type for the new item

### Return Values

A constructed Preferences menu item of the given type

UI\\Menu::appendQuit
====================

Append Quit Menu Item

### Description

<span class="modifier">public</span> <span
class="type">UI\\MenuItem</span> <span
class="methodname">UI\\Menu::appendQuit</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = UI\\MenuItem::class</span></span> \] )

Shall append a Quit menu item

### Parameters

`type`  
The type for the new item

### Return Values

A constructed Quit menu item of the given type

UI\\Menu::appendSeparator
=========================

Append Menu Item Separator

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Menu::appendSeparator</span> ( <span
class="methodparam">void</span> )

Shall append a separator

### Parameters

This function has no parameters.

UI\\Menu::\_\_construct
=======================

Construct a new Menu

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Menu::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Shall construct a new Menu

### Parameters

`name`  
The name (text) for the menu

Introduction
------------

Menu Items should only be created by the Menu

Class synopsis
--------------

**UI\\MenuItem**

<span class="ooclass"> class **UI\\MenuItem** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">enable</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isChecked</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onClick</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setChecked</span> ( <span class="methodparam"><span
class="type">bool</span> `$checked`</span> )

}

UI\\MenuItem::disable
=====================

Disable Menu Item

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\MenuItem::disable</span> ( <span
class="methodparam">void</span> )

Shall disable this Menu Item

### Parameters

This function has no parameters.

UI\\MenuItem::enable
====================

Enable Menu Item

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\MenuItem::enable</span> ( <span
class="methodparam">void</span> )

Shall enable this Menu Item

### Parameters

This function has no parameters.

UI\\MenuItem::isChecked
=======================

Detect Checked

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\MenuItem::isChecked</span> ( <span
class="methodparam">void</span> )

Shall detect if this Menu Item is checked

### Parameters

This function has no parameters.

UI\\MenuItem::onClick
=====================

On Click Callback

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\MenuItem::onClick</span> ( <span
class="methodparam">void</span> )

Shall be executed when this Menu Item is clicked

### Parameters

This function has no parameters.

UI\\MenuItem::setChecked
========================

Set Checked

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\MenuItem::setChecked</span> ( <span
class="methodparam"><span class="type">bool</span> `$checked`</span> )

Shall set the checked status of this Menu Item

### Parameters

`checked`  
The new status

Introduction
------------

An Area represents a canvas which can be used to draw, and respond to
mouse and key events.

Class synopsis
--------------

**UI\\Area**

<span class="ooclass"> class **UI\\Area** </span> <span class="ooclass">
<span class="modifier">extends</span> **UI\\Control** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Area::Ctrl` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Area::Alt` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Area::Shift` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Area::Super` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Area::Down` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Area::Up` ;

/\* Methods \*/

<span class="modifier">protected</span> <span
class="methodname">onDraw</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Pen</span> `$pen`</span> , <span
class="methodparam"><span class="type">UI\\Size</span>
`$areaSize`</span> , <span class="methodparam"><span
class="type">UI\\Point</span> `$clipPoint`</span> , <span
class="methodparam"><span class="type">UI\\Size</span>
`$clipSize`</span> )

<span class="modifier">protected</span> <span
class="methodname">onKey</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">int</span> `$ext`</span> , <span
class="methodparam"><span class="type">int</span> `$flags`</span> )

<span class="modifier">protected</span> <span
class="methodname">onMouse</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$areaPoint`</span> , <span
class="methodparam"><span class="type">UI\\Size</span>
`$areaSize`</span> , <span class="methodparam"><span
class="type">int</span> `$flags`</span> )

<span class="modifier">public</span> <span
class="methodname">redraw</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span
class="methodname">scrollTo</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> , <span
class="methodparam"><span class="type">UI\\Size</span> `$size`</span> )

<span class="modifier">public</span> <span
class="methodname">setSize</span> ( <span class="methodparam"><span
class="type">UI\\Size</span> `$size`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`UI\Area::Ctrl`**  
Shall be set in the modifiers passed to key and mouse events when the
CTRL key is active

**`UI\Area::Alt`**  
Shall be set in the modifiers passed to key and mouse events when the
ALT key is active

**`UI\Area::Shift`**  
Shall be set in the modifiers passed to key and mouse events when the
SHIFT key is active

**`UI\Area::Super`**  

**`UI\Area::Down`**  
Shall be set in the modifiers passed to key and mouse events

**`UI\Area::Up`**  
Shall be set in the modifiers passed to key and mouse events

UI\\Area::onDraw
================

Draw Callback

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Area::onDraw</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Pen</span>
`$pen`</span> , <span class="methodparam"><span
class="type">UI\\Size</span> `$areaSize`</span> , <span
class="methodparam"><span class="type">UI\\Point</span>
`$clipPoint`</span> , <span class="methodparam"><span
class="type">UI\\Size</span> `$clipSize`</span> )

Shall be invoked when this Area requires redrawing

### Parameters

`pen`  
A Pen suitable for drawing in this Area

`areaSize`  
The size of the Area

`clipPoint`  
The clip point of the Area

`clipSize`  
The clip size of the Area

UI\\Area::onKey
===============

Key Callback

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Area::onKey</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">int</span> `$ext`</span> ,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
)

Shall be executed on key events

### Parameters

`key`  
The key pressed

`ext`  
The extended key pressed

`flags`  
Event modifiers

### Return Values

UI\\Area::onMouse
=================

Mouse Callback

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Area::onMouse</span> ( <span
class="methodparam"><span class="type">UI\\Point</span>
`$areaPoint`</span> , <span class="methodparam"><span
class="type">UI\\Size</span> `$areaSize`</span> , <span
class="methodparam"><span class="type">int</span> `$flags`</span> )

Shall be executed on mouse events

### Parameters

`areaPoint`  
The co-ordinates of the event

`areaSize`  
The size of the area of the event

`flags`  
Event modifiers

UI\\Area::redraw
================

Redraw Area

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Area::redraw</span> ( <span
class="methodparam">void</span> )

Requests that this Area is redrawn

### Parameters

This function has no parameters.

### Return Values

UI\\Area::scrollTo
==================

Area Scroll

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Area::scrollTo</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
, <span class="methodparam"><span class="type">UI\\Size</span>
`$size`</span> )

Scroll this Area

### Parameters

`point`  
The point to scroll to

`size`  
The size of the scroll pane

UI\\Area::setSize
=================

Set Size

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Area::setSize</span> ( <span
class="methodparam"><span class="type">UI\\Size</span> `$size`</span> )

Sets the size of this Area

### Parameters

`size`  
The new size

Introduction
------------

This facility schedules repetitive execution of a callback, useful for
animations and other such activities.

Class synopsis
--------------

**UI\\Executor**

<span class="ooclass"> <span class="modifier">abstract</span> class
**UI\\Executor** </span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$microseconds`</span>
)

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$seconds`</span> ,
<span class="methodparam"><span class="type">int</span>
`$microseconds`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">kill</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">protected</span> <span class="type">void</span> <span
class="methodname">onExecute</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setInterval</span> ( <span
class="methodparam"><span class="type">int</span> `$microseconds`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setInterval</span> ( <span
class="methodparam"><span class="type">int</span> `$seconds`</span> ,
<span class="methodparam"><span class="type">int</span>
`$microseconds`</span> )

}

UI\\Executor::\_\_construct
===========================

Construct a new Executor

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Executor::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Executor::\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$microseconds`</span>
)

<span class="modifier">public</span> <span
class="methodname">UI\\Executor::\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$seconds`</span> ,
<span class="methodparam"><span class="type">int</span>
`$microseconds`</span> )

Shall construct an executor with the given interval, will not start
executing until main loop is entered

### Parameters

`seconds`  
Seconds between executions

`microseconds`  
Microseconds between executions

UI\\Executor::kill
==================

Stop Executor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">UI\\Executor::kill</span> ( <span
class="methodparam">void</span> )

Shall stop an executor, the executor cannot be restarted

### Parameters

This function has no parameters.

### Return Values

UI\\Executor::onExecute
=======================

Execution Callback

### Description

<span class="modifier">abstract</span> <span
class="modifier">protected</span> <span class="type">void</span> <span
class="methodname">UI\\Executor::onExecute</span> ( <span
class="methodparam">void</span> )

Shall be repetitively queued for execution in the main thread

### Parameters

This function has no parameters.

### Return Values

UI\\Executor::setInterval
=========================

Interval Manipulation

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Executor::setInterval</span> ( <span
class="methodparam"><span class="type">int</span> `$microseconds`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Executor::setInterval</span> ( <span
class="methodparam"><span class="type">int</span> `$seconds`</span> ,
<span class="methodparam"><span class="type">int</span>
`$microseconds`</span> )

Shall set the new interval. An interval of 0 will pause the executor
until a new interval has been set

### Parameters

`seconds`  

`microseconds`  

### Return Values

Indication of success

Introduction
------------

A Tab can contain many pages of Controls, each with a title, each
selectable by the user.

Class synopsis
--------------

**UI\\Controls\\Tab**

<span class="ooclass"> class **UI\\Controls\\Tab** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> `$controls` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">append</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> , <span
class="methodparam"><span class="type">UI\\Control</span>
`$control`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">delete</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasMargin</span> ( <span
class="methodparam"><span class="type">int</span> `$page`</span> )

<span class="modifier">public</span> <span
class="methodname">insertAt</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> , <span
class="methodparam"><span class="type">int</span> `$page`</span> , <span
class="methodparam"><span class="type">UI\\Control</span>
`$control`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">pages</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span
class="methodname">setMargin</span> ( <span class="methodparam"><span
class="type">int</span> `$page`</span> , <span class="methodparam"><span
class="type">bool</span> `$margin`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`controls`  
Contains controls, should not be manipulated directly

UI\\Controls\\Tab::append
=========================

Append Page

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Controls\\Tab::append</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">UI\\Control</span>
`$control`</span> )

Append a new page to this Tab

### Parameters

`name`  
The name for the new page

`control`  
The control for the new page

### Return Values

Shall return the index of the appended control, may be 0

UI\\Controls\\Tab::delete
=========================

Delete Page

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\Tab::delete</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Shall remove the selected page from this Tab

### Parameters

`index`  
The index of the page to remove

### Return Values

Indication of success

UI\\Controls\\Tab::hasMargin
============================

Margin Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\Tab::hasMargin</span> ( <span
class="methodparam"><span class="type">int</span> `$page`</span> )

Shall detect if the given page has a margin.

### Parameters

`page`  
The index of the page

### Return Values

UI\\Controls\\Tab::insertAt
===========================

Insert Page

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Tab::insertAt</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `$page`</span> ,
<span class="methodparam"><span class="type">UI\\Control</span>
`$control`</span> )

Shall insert a new page into this Tab

### Parameters

`name`  
The name for the new page

`page`  
The index to perform the insertion before

`control`  
The control for the new page

UI\\Controls\\Tab::pages
========================

Page Count

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Controls\\Tab::pages</span> ( <span
class="methodparam">void</span> )

Shall return the number of pages in this Tab

### Parameters

This function has no parameters.

### Return Values

The number of pages in this Tab

UI\\Controls\\Tab::setMargin
============================

Set Margin

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Tab::setMargin</span> ( <span
class="methodparam"><span class="type">int</span> `$page`</span> , <span
class="methodparam"><span class="type">bool</span> `$margin`</span> )

Shall enable or disable margins on the selected page

### Parameters

`page`  
The page to select

`margin`  
Margin switch

Introduction
------------

A Check is a labelled checkable box

Class synopsis
--------------

**UI\\Controls\\Check**

<span class="ooclass"> class **UI\\Controls\\Check** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getText</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isChecked</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onToggle</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setChecked</span> ( <span class="methodparam"><span
class="type">bool</span> `$checked`</span> )

<span class="modifier">public</span> <span
class="methodname">setText</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

UI\\Controls\\Check::\_\_construct
==================================

Construct a new Check

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Check::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall construct a new Check

### Parameters

`text`  
The text (label) for the Check box

UI\\Controls\\Check::getText
============================

Get Text

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">UI\\Controls\\Check::getText</span> ( <span
class="methodparam">void</span> )

Shall return the text (label) for this Check

### Parameters

This function has no parameters.

### Return Values

The current text (label)

UI\\Controls\\Check::isChecked
==============================

Checked Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\Check::isChecked</span> ( <span
class="methodparam">void</span> )

Shall detect the status of this Check

### Parameters

This function has no parameters.

UI\\Controls\\Check::onToggle
=============================

Toggle Callback

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Controls\\Check::onToggle</span> ( <span
class="methodparam">void</span> )

Shall be executed when the status of this Check is changed

### Parameters

This function has no parameters.

UI\\Controls\\Check::setChecked
===============================

Set Checked

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Check::setChecked</span> ( <span
class="methodparam"><span class="type">bool</span> `$checked`</span> )

Shall change the status of this Check

### Parameters

`checked`  
The new status

UI\\Controls\\Check::setText
============================

Set Text

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Check::setText</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall set the text (label) for this Check

### Parameters

`text`  
The new text (label)

Introduction
------------

Represents a labelled clickable button

Class synopsis
--------------

**UI\\Controls\\Button**

<span class="ooclass"> class **UI\\Controls\\Button** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getText</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onClick</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setText</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

UI\\Controls\\Button::\_\_construct
===================================

Construct a new Button

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Button::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall construct a new Button

### Parameters

`text`  
The text (label) for this Button

UI\\Controls\\Button::getText
=============================

Get Text

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">UI\\Controls\\Button::getText</span> ( <span
class="methodparam">void</span> )

Shall retrieve the text (label) for this Button

### Parameters

This function has no parameters.

### Return Values

The current text (label)

UI\\Controls\\Button::onClick
=============================

Click Handler

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Controls\\Button::onClick</span> ( <span
class="methodparam">void</span> )

Shall be executed when this Button is clicked

### Parameters

This function has no parameters.

UI\\Controls\\Button::setText
=============================

Set Text

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Button::setText</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall set the text (label) for this Button

### Parameters

`text`  
The new text (label)

Introduction
------------

A Color Button is a button which displays a color picker when clicked

Class synopsis
--------------

**UI\\Controls\\ColorButton**

<span class="ooclass"> class **UI\\Controls\\ColorButton** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">UI\\Color</span>
<span class="methodname">getColor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onChange</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setColor</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Color</span> `$color`</span> )

<span class="modifier">public</span> <span
class="methodname">setColor</span> ( <span class="methodparam"><span
class="type">int</span> `$color`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

UI\\Controls\\ColorButton::getColor
===================================

Get Color

### Description

<span class="modifier">public</span> <span class="type">UI\\Color</span>
<span class="methodname">UI\\Controls\\ColorButton::getColor</span> (
<span class="methodparam">void</span> )

Shall retrieve the currently selected Color

### Parameters

This function has no parameters.

### Return Values

UI\\Controls\\ColorButton::onChange
===================================

Change Handler

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Controls\\ColorButton::onChange</span> ( <span
class="methodparam">void</span> )

Shall be executed when the selected Color is changed

### Parameters

This function has no parameters.

UI\\Controls\\ColorButton::setColor
===================================

Set Color

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\ColorButton::setColor</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\ColorButton::setColor</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> )

Shall set the currently selected Color

### Parameters

`color`  
The new color

Introduction
------------

A Label is a single line of text, meant to identify, for the user, some
element of the interface.

Class synopsis
--------------

**UI\\Controls\\Label**

<span class="ooclass"> class **UI\\Controls\\Label** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getText</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setText</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

UI\\Controls\\Label::\_\_construct
==================================

Construct a new Label

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Label::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall construct a new Label

### Parameters

`text`  
The text for this label

UI\\Controls\\Label::getText
============================

Get Text

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">UI\\Controls\\Label::getText</span> ( <span
class="methodparam">void</span> )

Shall return the current text for this Label

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

UI\\Controls\\Label::setText
============================

Set Text

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Label::setText</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall set the text for this Label

### Parameters

`text`  
The new text

Introduction
------------

An Entry is a text entry control, suitable for entering plain text,
passwords, or search terms.

Class synopsis
--------------

**UI\\Controls\\Entry**

<span class="ooclass"> class **UI\\Controls\\Entry** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Entry::Normal` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Entry::Password` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Entry::Search` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = UI\\Controls\\Entry::Normal</span></span> \] )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getText</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isReadOnly</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onChange</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setReadOnly</span> ( <span class="methodparam"><span
class="type">bool</span> `$readOnly`</span> )

<span class="modifier">public</span> <span
class="methodname">setText</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`UI\Controls\Entry::Normal`**  
A normal single line entry

**`UI\Controls\Entry::Password`**  
A password entry

**`UI\Controls\Entry::Search`**  
A search entry

UI\\Controls\\Entry::\_\_construct
==================================

Construct a new Entry

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Entry::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = UI\\Controls\\Entry::Normal</span></span> \] )

Construct a new entry of the given type

### Parameters

`type`  
Entry::Normal, Entry::Password, or Entry::Search

UI\\Controls\\Entry::getText
============================

Get Text

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">UI\\Controls\\Entry::getText</span> ( <span
class="methodparam">void</span> )

Shall return the current text from this Entry

### Parameters

This function has no parameters.

### Return Values

The current text

UI\\Controls\\Entry::isReadOnly
===============================

Detect Read Only

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\Entry::isReadOnly</span> ( <span
class="methodparam">void</span> )

Shall detect if this Entry is read only

### Parameters

This function has no parameters.

### Return Values

UI\\Controls\\Entry::onChange
=============================

Change Handler

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Controls\\Entry::onChange</span> ( <span
class="methodparam">void</span> )

Shall be executed when the text in this Entry changes

### Parameters

This function has no parameters.

UI\\Controls\\Entry::setReadOnly
================================

Set Read Only

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Entry::setReadOnly</span> ( <span
class="methodparam"><span class="type">bool</span> `$readOnly`</span> )

Shall enable or disable read only for this Entry

### Parameters

`readOnly`  

UI\\Controls\\Entry::setText
============================

Set Text

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Entry::setText</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall set the text for this Entry

### Parameters

`text`  
The new text

Introduction
------------

A Multiline Entry is a text entry control able to hold multiple lines of
text, with or without wrapping.

Class synopsis
--------------

**UI\\Controls\\MultilineEntry**

<span class="ooclass"> class **UI\\Controls\\MultilineEntry** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**UI\\Control** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\MultilineEntry::Wrap` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\MultilineEntry::NoWrap` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$type`</span> \] )

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">append</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getText</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isReadOnly</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onChange</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setReadOnly</span> ( <span class="methodparam"><span
class="type">bool</span> `$readOnly`</span> )

<span class="modifier">public</span> <span
class="methodname">setText</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`UI\Controls\MultilineEntry::Wrap`**  
Allow lines to wrap

**`UI\Controls\MultilineEntry::NoWrap`**  
Do not allow lines to wrap

UI\\Controls\\MultilineEntry::append
====================================

Append Text

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\MultilineEntry::append</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall append the given text to the text in this Multiline Entry

### Parameters

`text`  
The text to append

UI\\Controls\\MultilineEntry::\_\_construct
===========================================

Construct a new Multiline Entry

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\MultilineEntry::\_\_construct</span>
(\[ <span class="methodparam"><span class="type">int</span>
`$type`</span> \] )

Shall construct a new Multiline Entry of the given type

### Parameters

`type`  
MultilineEntry::Wrap or MultilineEntry::NoWrap

UI\\Controls\\MultilineEntry::getText
=====================================

Get Text

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">UI\\Controls\\MultilineEntry::getText</span> (
<span class="methodparam">void</span> )

Shall return the text in this Multiline Entry

### Parameters

This function has no parameters.

UI\\Controls\\MultilineEntry::isReadOnly
========================================

Read Only Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\MultilineEntry::isReadOnly</span>
( <span class="methodparam">void</span> )

Shall detect if this Multiline Entry is read only

### Parameters

This function has no parameters.

UI\\Controls\\MultilineEntry::onChange
======================================

Change Handler

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Controls\\MultilineEntry::onChange</span> ( <span
class="methodparam">void</span> )

Shall be executed when the text in this Multiline Entry is changed

### Parameters

This function has no parameters.

UI\\Controls\\MultilineEntry::setReadOnly
=========================================

Set Read Only

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\MultilineEntry::setReadOnly</span> (
<span class="methodparam"><span class="type">bool</span>
`$readOnly`</span> )

Shall enable or disable read only on this Multiline Entry

### Parameters

`readOnly`  

UI\\Controls\\MultilineEntry::setText
=====================================

Set Text

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\MultilineEntry::setText</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall set the text in this Multiline Entry

### Parameters

`text`  
The new text

Introduction
------------

A Spin box is a text box with an up-down control which changes the
integer value in the box, within a defined range

Class synopsis
--------------

**UI\\Controls\\Spin**

<span class="ooclass"> class **UI\\Controls\\Spin** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$min`</span> , <span
class="methodparam"><span class="type">int</span> `$max`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getValue</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onChange</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setValue</span> ( <span class="methodparam"><span
class="type">int</span> `$value`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

UI\\Controls\\Spin::\_\_construct
=================================

Construct a new Spin

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Spin::\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$min`</span> , <span
class="methodparam"><span class="type">int</span> `$max`</span> )

Constructs a new Spin with the given range

### Parameters

`min`  
The minimum value allowed

`max`  
The maximum value allowed

UI\\Controls\\Spin::getValue
============================

Get Value

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Controls\\Spin::getValue</span> ( <span
class="methodparam">void</span> )

Get the value in this Spin

### Parameters

This function has no parameters.

UI\\Controls\\Spin::onChange
============================

Change Handler

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Controls\\Spin::onChange</span> ( <span
class="methodparam">void</span> )

Shall be executed when the value in this Spin changes

### Parameters

This function has no parameters.

UI\\Controls\\Spin::setValue
============================

Set Value

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Spin::setValue</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

Set the value in this Spin

### Parameters

`value`  
The new value

Introduction
------------

A Slider is a control which represents a range, and a current value in
the range. The sliding element of the control (sometimes called the
"thumb") reflects the value, and can be adjusted within the range.

Class synopsis
--------------

**UI\\Controls\\Slider**

<span class="ooclass"> class **UI\\Controls\\Slider** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$min`</span> , <span
class="methodparam"><span class="type">int</span> `$max`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getValue</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onChange</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setValue</span> ( <span class="methodparam"><span
class="type">int</span> `$value`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

UI\\Controls\\Slider::\_\_construct
===================================

Construct a new Slider

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Slider::\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$min`</span> , <span
class="methodparam"><span class="type">int</span> `$max`</span> )

Construct a new Slider with the given range

### Parameters

`min`  
The minimum allowed value

`max`  
The maximum allowed value

UI\\Controls\\Slider::getValue
==============================

Get Value

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Controls\\Slider::getValue</span> ( <span
class="methodparam">void</span> )

Get the value from this Slider

### Parameters

This function has no parameters.

UI\\Controls\\Slider::onChange
==============================

Change Handler

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Controls\\Slider::onChange</span> ( <span
class="methodparam">void</span> )

Shall be executed when the value of this Slider changes

### Parameters

This function has no parameters.

UI\\Controls\\Slider::setValue
==============================

Set Value

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Slider::setValue</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

Shall set the value for this Slider

### Parameters

`value`  
The new value

Introduction
------------

A Progress control is a familiar Progress bar: It represents progress as
a percentage, with a possible range of 0 to 100 (inclusive).

Class synopsis
--------------

**UI\\Controls\\Progress**

<span class="ooclass"> class **UI\\Controls\\Progress** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getValue</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setValue</span> ( <span class="methodparam"><span
class="type">int</span> `$value`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

UI\\Controls\\Progress::getValue
================================

Get Value

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Controls\\Progress::getValue</span> ( <span
class="methodparam">void</span> )

Shall retrieve the current value of this Progress bar

### Parameters

This function has no parameters.

UI\\Controls\\Progress::setValue
================================

Set Value

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Progress::setValue</span> ( <span
class="methodparam"><span class="type">int</span> `$value`</span> )

Shall set the value for this Progress bar

### Parameters

`value`  
An integer between 0 and 100 (inclusive)

Introduction
------------

A Separator represents a control separator, it has no other function.

Class synopsis
--------------

**UI\\Controls\\Separator**

<span class="ooclass"> class **UI\\Controls\\Separator** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Separator::Horizontal` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Separator::Vertical` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = UI\\Controls\\Separator::Horizontal</span></span>
\] )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`UI\Controls\Separator::Horizontal`**  
A Horizontal Separator

**`UI\Controls\Separator::Vertical`**  
A Vertical Separator

UI\\Controls\\Separator::\_\_construct
======================================

Construct a new Separator

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Separator::\_\_construct</span> (\[
<span class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = UI\\Controls\\Separator::Horizontal</span></span>
\] )

Shall construct a new Separator of the given type

### Parameters

`type`  
Separator::Horizonal or Separator::Vertical

Introduction
------------

A Combo control represents a list of options, like the familiar select
HTML element.

Class synopsis
--------------

**UI\\Controls\\Combo**

<span class="ooclass"> class **UI\\Controls\\Combo** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">append</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getSelected</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onSelected</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setSelected</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

UI\\Controls\\Combo::append
===========================

Append Option

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Combo::append</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Append an option to this Combo

### Parameters

`text`  
The text for the new option

UI\\Controls\\Combo::getSelected
================================

Get Selected Option

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Controls\\Combo::getSelected</span> ( <span
class="methodparam">void</span> )

Shall retrieve the index of the option selected in this Combo

### Parameters

This function has no parameters.

UI\\Controls\\Combo::onSelected
===============================

Selected Handler

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Controls\\Combo::onSelected</span> ( <span
class="methodparam">void</span> )

Shall be executed when an option is selected in this Combo

### Parameters

This function has no parameters.

UI\\Controls\\Combo::setSelected
================================

Set Selected Option

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Combo::setSelected</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Shall set the currently selected option in this Combo

### Parameters

`index`  
The index of the option to select

Introduction
------------

An Editable Combo is a Combo which allows the user to enter custom
options

Class synopsis
--------------

**UI\\Controls\\EditableCombo**

<span class="ooclass"> class **UI\\Controls\\EditableCombo** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**UI\\Control** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">append</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getText</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onChange</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setText</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

UI\\Controls\\EditableCombo::append
===================================

Append Option

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\EditableCombo::append</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall append a new option to this Editable Combo

### Parameters

`text`  
The text for the new option

UI\\Controls\\EditableCombo::getText
====================================

Get Text

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">UI\\Controls\\EditableCombo::getText</span> (
<span class="methodparam">void</span> )

Get the value of the currently selected option in this Editable Combo

### Parameters

This function has no parameters.

UI\\Controls\\EditableCombo::onChange
=====================================

Change Handler

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Controls\\EditableCombo::onChange</span> ( <span
class="methodparam">void</span> )

Shall be executed when the value of this Editable Combobox changes

### Parameters

This function has no parameters.

UI\\Controls\\EditableCombo::setText
====================================

Set Text

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\EditableCombo::setText</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall set the text of the currently selected option in this Editable
Combo

### Parameters

`text`  
The new text

Introduction
------------

A Radio is similar to the radio input type familiar from HTML

Class synopsis
--------------

**UI\\Controls\\Radio**

<span class="ooclass"> class **UI\\Controls\\Radio** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">append</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getSelected</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span
class="methodname">onSelected</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setSelected</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

UI\\Controls\\Radio::append
===========================

Append Option

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Radio::append</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Shall append a new option to this Radio

### Parameters

`text`  
The text (label) for the option

UI\\Controls\\Radio::getSelected
================================

Get Selected Option

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Controls\\Radio::getSelected</span> ( <span
class="methodparam">void</span> )

Shall retrieve the index of the currently selected option in this Radio

### Parameters

This function has no parameters.

UI\\Controls\\Radio::onSelected
===============================

Selected Handler

### Description

<span class="modifier">protected</span> <span
class="methodname">UI\\Controls\\Radio::onSelected</span> ( <span
class="methodparam">void</span> )

Shall be executed when the option selected in this Radio changes

### Parameters

This function has no parameters.

UI\\Controls\\Radio::setSelected
================================

Set Selected Option

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Radio::setSelected</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Shall set the currently selected option in this Radio

### Parameters

`index`  
The index of the option to select

Introduction
------------

A Picker represents a button which when clicked presents a native
Date/Time/DateTime Picker interface to the user.

Class synopsis
--------------

**UI\\Controls\\Picker**

<span class="ooclass"> class **UI\\Controls\\Picker** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Picker::Date` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Picker::Time` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Picker::DateTime` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = UI\\Controls\\Picker::Date</span></span> \] )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`UI\Controls\Picker::Date`**  
A Date Picker

**`UI\Controls\Picker::Time`**  
A Time Picker

**`UI\Controls\Picker::DateTime`**  
A Date and Time Picker

UI\\Controls\\Picker::\_\_construct
===================================

Construct a new Picker

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Picker::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = UI\\Controls\\Picker::Date</span></span> \] )

Construct a new Picker of the given type

### Parameters

`type`  
Picker::Date, Picker::Time, or Picker::DateTime

Introduction
------------

A Form is a control which allows the arrangement of other controls into
a familiar layout (the form).

Class synopsis
--------------

**UI\\Controls\\Form**

<span class="ooclass"> class **UI\\Controls\\Form** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> `$controls` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">append</span> ( <span class="methodparam"><span
class="type">string</span> `$label`</span> , <span
class="methodparam"><span class="type">UI\\Control</span>
`$control`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$stretchy`<span class="initializer"> =
**`false`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">delete</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPadded</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setPadded</span> ( <span class="methodparam"><span
class="type">bool</span> `$padded`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`controls`  
Contains controls, should not be manipulated directly

UI\\Controls\\Form::append
==========================

Append Control

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Controls\\Form::append</span> ( <span
class="methodparam"><span class="type">string</span> `$label`</span> ,
<span class="methodparam"><span class="type">UI\\Control</span>
`$control`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$stretchy`<span class="initializer"> =
**`false`**</span></span> \] )

Shall append the control to the form, and set the label

### Parameters

`label`  
The text for the label

`control`  
A control

`stretchy`  
Should be set true to stretch the control

### Return Values

Shall return the index of the appended control, may be 0

UI\\Controls\\Form::delete
==========================

Delete Control

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\Form::delete</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Shall delete the control at the given index in this Form

### Parameters

`index`  
The index of the control to remove

### Return Values

Indication of succcess

UI\\Controls\\Form::isPadded
============================

Padding Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\Form::isPadded</span> ( <span
class="methodparam">void</span> )

Shall detect if padding is enabled on this Form

### Parameters

This function has no parameters.

UI\\Controls\\Form::setPadded
=============================

Set Padding

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Form::setPadded</span> ( <span
class="methodparam"><span class="type">bool</span> `$padded`</span> )

Shall enable or disable padding on this Form

### Parameters

`padded`  

Introduction
------------

A Grid is a control which is allows the arrangement of children into a
grid

Class synopsis
--------------

**UI\\Controls\\Grid**

<span class="ooclass"> class **UI\\Controls\\Grid** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Grid::Fill` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Grid::Start` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Grid::Center` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Grid::End` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Grid::Leading` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Grid::Top` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Grid::Trailing` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Grid::Bottom` ;

/\* Properties \*/

<span class="modifier">protected</span> `$controls` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">append</span> ( <span class="methodparam"><span
class="type">UI\\Control</span> `$control`</span> , <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">int</span> `$xspan`</span> ,
<span class="methodparam"><span class="type">int</span> `$yspan`</span>
, <span class="methodparam"><span class="type">bool</span>
`$hexpand`</span> , <span class="methodparam"><span
class="type">int</span> `$halign`</span> , <span
class="methodparam"><span class="type">bool</span> `$vexpand`</span> ,
<span class="methodparam"><span class="type">int</span> `$valign`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPadded</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setPadded</span> ( <span class="methodparam"><span
class="type">bool</span> `$padding`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`UI\Controls\Grid::Fill`**  

**`UI\Controls\Grid::Start`**  

**`UI\Controls\Grid::Center`**  

**`UI\Controls\Grid::End`**  

**`UI\Controls\Grid::Leading`**  

**`UI\Controls\Grid::Top`**  

**`UI\Controls\Grid::Trailing`**  

**`UI\Controls\Grid::Bottom`**  

Properties
----------

`controls`  
Contains controls, should not be manipulated directly

UI\\Controls\\Grid::append
==========================

Append Control

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Grid::append</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$control`</span> , <span class="methodparam"><span
class="type">int</span> `$left`</span> , <span class="methodparam"><span
class="type">int</span> `$top`</span> , <span class="methodparam"><span
class="type">int</span> `$xspan`</span> , <span
class="methodparam"><span class="type">int</span> `$yspan`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$hexpand`</span> , <span class="methodparam"><span
class="type">int</span> `$halign`</span> , <span
class="methodparam"><span class="type">bool</span> `$vexpand`</span> ,
<span class="methodparam"><span class="type">int</span> `$valign`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`control`  
The Control to append

`left`  

`top`  

`xspan`  

`yspan`  

`hexpand`  

`halign`  

`vexpand`  

`valign`  

### Return Values

UI\\Controls\\Grid::isPadded
============================

Padding Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\Grid::isPadded</span> ( <span
class="methodparam">void</span> )

Shall detect if padding is enabled on this Grid

### Parameters

This function has no parameters.

UI\\Controls\\Grid::setPadded
=============================

Set Padding

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Grid::setPadded</span> ( <span
class="methodparam"><span class="type">bool</span> `$padding`</span> )

Shall enable or disable padding for this Grid

### Parameters

`padding`  

Introduction
------------

A Group is a titled container for child controls

Class synopsis
--------------

**UI\\Controls\\Group**

<span class="ooclass"> class **UI\\Controls\\Group** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> `$controls` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">append</span> ( <span class="methodparam"><span
class="type">UI\\Control</span> `$control`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getTitle</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasMargin</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setMargin</span> ( <span class="methodparam"><span
class="type">bool</span> `$margin`</span> )

<span class="modifier">public</span> <span
class="methodname">setTitle</span> ( <span class="methodparam"><span
class="type">string</span> `$title`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`controls`  
Contains controls, should not be manipulated directly

UI\\Controls\\Group::append
===========================

Append Control

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Group::append</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$control`</span> )

Shall append a control to this Group

### Parameters

`control`  
The control to append

UI\\Controls\\Group::\_\_construct
==================================

Construct a new Group

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Group::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> )

Shall construct a new Group with the given title

### Parameters

`title`  
The text for the title label

UI\\Controls\\Group::getTitle
=============================

Get Title

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">UI\\Controls\\Group::getTitle</span> ( <span
class="methodparam">void</span> )

Shall return the current title for this Group

### Parameters

This function has no parameters.

### Return Values

The current title

UI\\Controls\\Group::hasMargin
==============================

Margin Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\Group::hasMargin</span> ( <span
class="methodparam">void</span> )

Shall detect if this Group has a margin

### Parameters

This function has no parameters.

UI\\Controls\\Group::setMargin
==============================

Set Margin

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Group::setMargin</span> ( <span
class="methodparam"><span class="type">bool</span> `$margin`</span> )

Shall enable or disable margins for this Group

### Parameters

`margin`  

UI\\Controls\\Group::setTitle
=============================

Set Title

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Group::setTitle</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> )

Shall set the title for this Group

### Parameters

`title`  
The text for the new title

Introduction
------------

A Box allows the arrangement of other controls

Class synopsis
--------------

**UI\\Controls\\Box**

<span class="ooclass"> class **UI\\Controls\\Box** </span> <span
class="ooclass"> <span class="modifier">extends</span> **UI\\Control**
</span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Box::Vertical` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Controls\Box::Horizontal` ;

/\* Properties \*/

<span class="modifier">protected</span> `$controls` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$orientation`<span
class="initializer"> = UI\\Controls\\Box::Horizontal</span></span> \] )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">append</span> ( <span class="methodparam"><span
class="type">Control</span> `$control`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$stretchy`<span
class="initializer"> = **`false`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">delete</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getOrientation</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPadded</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setPadded</span> ( <span class="methodparam"><span
class="type">bool</span> `$padded`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="methodname">UI\\Control::destroy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::disable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::enable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Control</span> <span
class="methodname">UI\\Control::getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Control::getTopLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::hide</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Control::isVisible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::setParent</span> ( <span
class="methodparam"><span class="type">UI\\Control</span>
`$parent`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Control::show</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`controls`  
Contains controls, should not be manipulated directly

Predefined Constants
--------------------

**`UI\Controls\Box::Vertical`**  

**`UI\Controls\Box::Horizontal`**  

UI\\Controls\\Box::append
=========================

Append Control

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Controls\\Box::append</span> ( <span
class="methodparam"><span class="type">Control</span> `$control`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$stretchy`<span class="initializer"> = **`false`**</span></span> \] )

Shall append the given control to this Box

### Parameters

`control`  
The control to append

`stretchy`  
Set true to stretch the control

### Return Values

Shall return the index of the appended control, may be 0

UI\\Controls\\Box::\_\_construct
================================

Construct a new Box

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Box::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$orientation`<span
class="initializer"> = UI\\Controls\\Box::Horizontal</span></span> \] )

Shall construct a new box

### Parameters

`orientation`  
Box::Horizontal or Box::Vertical

UI\\Controls\\Box::delete
=========================

Delete Control

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\Box::delete</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Shall delete the control at the given index from this Box

### Parameters

`index`  
The index of the control to delete

### Return Values

Indication of success

UI\\Controls\\Box::getOrientation
=================================

Get Orientation

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Controls\\Box::getOrientation</span> ( <span
class="methodparam">void</span> )

Shall retrieve the orientation of this Box

### Parameters

This function has no parameters.

UI\\Controls\\Box::isPadded
===========================

Padding Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Controls\\Box::isPadded</span> ( <span
class="methodparam">void</span> )

Shall detect if padding is enabled on this Box

### Parameters

This function has no parameters.

UI\\Controls\\Box::setPadded
============================

Set Padding

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Controls\\Box::setPadded</span> ( <span
class="methodparam"><span class="type">bool</span> `$padded`</span> )

Shall enable or disable padding on this Box

### Parameters

`padded`  

Introduction
------------

The Pen is passed to the Area Draw event handler, it is used for
clipping, filling, stroking, and writing to Draw Paths.

Class synopsis
--------------

**UI\\Draw\\Pen**

<span class="ooclass"> <span class="modifier">final</span> class
**UI\\Draw\\Pen** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">clip</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Path</span> `$path`</span> )

<span class="modifier">public</span> <span
class="methodname">fill</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Path</span> `$path`</span> , <span
class="methodparam"><span class="type">UI\\Draw\\Brush</span>
`$with`</span> )

<span class="modifier">public</span> <span
class="methodname">fill</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Path</span> `$path`</span> , <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$with`</span> )

<span class="modifier">public</span> <span
class="methodname">fill</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Path</span> `$path`</span> , <span
class="methodparam"><span class="type">int</span> `$with`</span> )

<span class="modifier">public</span> <span
class="methodname">restore</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">save</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">stroke</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Path</span> `$path`</span> , <span
class="methodparam"><span class="type">UI\\Draw\\Brush</span>
`$with`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Stroke</span> `$stroke`</span> )

<span class="modifier">public</span> <span
class="methodname">stroke</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Path</span> `$path`</span> , <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$with`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Stroke</span> `$stroke`</span> )

<span class="modifier">public</span> <span
class="methodname">stroke</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Path</span> `$path`</span> , <span
class="methodparam"><span class="type">int</span> `$with`</span> , <span
class="methodparam"><span class="type">UI\\Draw\\Stroke</span>
`$stroke`</span> )

<span class="modifier">public</span> <span
class="methodname">transform</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Matrix</span> `$matrix`</span> )

<span class="modifier">public</span> <span
class="methodname">write</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> , <span
class="methodparam"><span class="type">UI\\Draw\\Text\\Layout</span>
`$layout`</span> )

}

UI\\Draw\\Pen::clip
===================

Clip a Path

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::clip</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Path</span>
`$path`</span> )

Shall clip the given Path

### Parameters

`path`  
The path to clip

UI\\Draw\\Pen::fill
===================

Fill a Path

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::fill</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Path</span>
`$path`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Brush</span> `$with`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::fill</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Path</span>
`$path`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Color</span> `$with`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::fill</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Path</span>
`$path`</span> , <span class="methodparam"><span class="type">int</span>
`$with`</span> )

Shall fill the given path

### Parameters

`path`  
The path to fill

`with`  
The color or brush to fill with

UI\\Draw\\Pen::restore
======================

Restore

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::restore</span> ( <span
class="methodparam">void</span> )

Shall restore a previously saved Pen

### Parameters

This function has no parameters.

UI\\Draw\\Pen::save
===================

Save

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::save</span> ( <span
class="methodparam">void</span> )

Shall save the Pen

### Parameters

This function has no parameters.

UI\\Draw\\Pen::stroke
=====================

Stroke a Path

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::stroke</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Path</span>
`$path`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Brush</span> `$with`</span> , <span
class="methodparam"><span class="type">UI\\Draw\\Stroke</span>
`$stroke`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::stroke</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Path</span>
`$path`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Color</span> `$with`</span> , <span
class="methodparam"><span class="type">UI\\Draw\\Stroke</span>
`$stroke`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::stroke</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Path</span>
`$path`</span> , <span class="methodparam"><span class="type">int</span>
`$with`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Stroke</span> `$stroke`</span> )

Shall stroke the given path

### Parameters

`path`  
The path to stroke

`with`  
The color or brush to stroke with

`stroke`  
The configuration of the stroke

UI\\Draw\\Pen::transform
========================

Matrix Transform

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::transform</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Matrix</span>
`$matrix`</span> )

Shall perform matrix transformation

### Parameters

`matrix`  
The matrix to use

UI\\Draw\\Pen::write
====================

Draw Text at Point

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Pen::write</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
, <span class="methodparam"><span
class="type">UI\\Draw\\Text\\Layout</span> `$layout`</span> )

Shall draw the given text layout at the given point

### Parameters

`point`  
The point to perform the drawing

`layout`  
The layout of the text to draw

Introduction
------------

A Draw Path guides a Draw Pen, telling the Pen where to draw on an Area.

Class synopsis
--------------

**UI\\Draw\\Path**

<span class="ooclass"> class **UI\\Draw\\Path** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Path::Winding` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Path::Alternate` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = UI\\Draw\\Path::Winding</span></span> \] )

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">addRectangle</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> , <span
class="methodparam"><span class="type">UI\\Size</span> `$size`</span> )

<span class="modifier">public</span> <span
class="methodname">arcTo</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> , <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$angle`</span> , <span class="methodparam"><span
class="type">float</span> `$sweep`</span> , <span
class="methodparam"><span class="type">float</span> `$negative`</span> )

<span class="modifier">public</span> <span
class="methodname">bezierTo</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> , <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$angle`</span> , <span class="methodparam"><span
class="type">float</span> `$sweep`</span> , <span
class="methodparam"><span class="type">float</span> `$negative`</span> )

<span class="modifier">public</span> <span
class="methodname">closeFigure</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="methodname">end</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">lineTo</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> , <span
class="methodparam"><span class="type">float</span> `$radius`</span> ,
<span class="methodparam"><span class="type">float</span>
`$angle`</span> , <span class="methodparam"><span
class="type">float</span> `$sweep`</span> , <span
class="methodparam"><span class="type">float</span> `$negative`</span> )

<span class="modifier">public</span> <span
class="methodname">newFigure</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> )

<span class="modifier">public</span> <span
class="methodname">newFigureWithArc</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
, <span class="methodparam"><span class="type">float</span>
`$radius`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> , <span
class="methodparam"><span class="type">float</span> `$sweep`</span> ,
<span class="methodparam"><span class="type">float</span>
`$negative`</span> )

}

Predefined Constants
--------------------

**`UI\Draw\Path::Winding`**  
This is the default draw path mode

**`UI\Draw\Path::Alternate`**  
This is the alternate draw path mode

UI\\Draw\\Path::addRectangle
============================

Draw a Rectangle

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Path::addRectangle</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
, <span class="methodparam"><span class="type">UI\\Size</span>
`$size`</span> )

Shall map the path of a rectangle of the given size, at the given point

### Parameters

`point`  
The point to begin the shape

`size`  
The size of the rectangle

UI\\Draw\\Path::arcTo
=====================

Draw an Arc

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Path::arcTo</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
, <span class="methodparam"><span class="type">float</span>
`$radius`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> , <span
class="methodparam"><span class="type">float</span> `$sweep`</span> ,
<span class="methodparam"><span class="type">float</span>
`$negative`</span> )

Shall map the path for an arc

### Parameters

`point`  
The point to begin mapping

`radius`  
The radius of the arc

`angle`  
The angle of the arc

`sweep`  
The sweep of the arc

`negative`  

### Return Values

UI\\Draw\\Path::bezierTo
========================

Draw Bezier Curve

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Path::bezierTo</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
, <span class="methodparam"><span class="type">float</span>
`$radius`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> , <span
class="methodparam"><span class="type">float</span> `$sweep`</span> ,
<span class="methodparam"><span class="type">float</span>
`$negative`</span> )

Shall draw a bezier curve

### Parameters

`point`  
The point at which to begin mapping

`radius`  
The radius of the curve

`angle`  
The angle of the curve

`sweep`  
The sweep of the curve

`negative`  

UI\\Draw\\Path::closeFigure
===========================

Close Figure

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Path::closeFigure</span> ( <span
class="methodparam">void</span> )

Shall close the current figure

### Parameters

This function has no parameters.

UI\\Draw\\Path::\_\_construct
=============================

Construct a new Path

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Path::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = UI\\Draw\\Path::Winding</span></span> \] )

Shall construct a new path in the given mode

### Parameters

`mode`  
Path::Winding or Path::Alternate

UI\\Draw\\Path::end
===================

Finalize Path

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Path::end</span> ( <span
class="methodparam">void</span> )

Shall finalize this Path

### Parameters

This function has no parameters.

UI\\Draw\\Path::lineTo
======================

Draw a Line

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Path::lineTo</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
, <span class="methodparam"><span class="type">float</span>
`$radius`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> , <span
class="methodparam"><span class="type">float</span> `$sweep`</span> ,
<span class="methodparam"><span class="type">float</span>
`$negative`</span> )

Shall map the path for a line

### Parameters

`point`  
The point to begin mapping

`radius`  

`angle`  

`sweep`  

`negative`  

### Return Values

UI\\Draw\\Path::newFigure
=========================

Draw Figure

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Path::newFigure</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
)

Shall map a new figure at the given point

### Parameters

`point`  
The point to begin mapping

UI\\Draw\\Path::newFigureWithArc
================================

Draw Figure with Arc

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Path::newFigureWithArc</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
, <span class="methodparam"><span class="type">float</span>
`$radius`</span> , <span class="methodparam"><span
class="type">float</span> `$angle`</span> , <span
class="methodparam"><span class="type">float</span> `$sweep`</span> ,
<span class="methodparam"><span class="type">float</span>
`$negative`</span> )

### Parameters

`point`  

`radius`  

`angle`  

`sweep`  

`negative`  

### Return Values

Introduction
------------

Class synopsis
--------------

**UI\\Draw\\Matrix**

<span class="ooclass"> class **UI\\Draw\\Matrix** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">invert</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isInvertible</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">UI\\Draw\\Matrix</span> <span
class="methodname">multiply</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Matrix</span> `$matrix`</span> )

<span class="modifier">public</span> <span
class="methodname">rotate</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> , <span
class="methodparam"><span class="type">float</span> `$amount`</span> )

<span class="modifier">public</span> <span
class="methodname">scale</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$center`</span> , <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
)

<span class="modifier">public</span> <span
class="methodname">skew</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> , <span
class="methodparam"><span class="type">UI\\Point</span> `$amount`</span>
)

<span class="modifier">public</span> <span
class="methodname">translate</span> ( <span class="methodparam"><span
class="type">UI\\Point</span> `$point`</span> )

}

UI\\Draw\\Matrix::invert
========================

Invert Matrix

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Matrix::invert</span> ( <span
class="methodparam">void</span> )

Shall invert this matrix

### Parameters

This function has no parameters.

UI\\Draw\\Matrix::isInvertible
==============================

Invertible Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Draw\\Matrix::isInvertible</span> ( <span
class="methodparam">void</span> )

Shall detect if this Matrix may be inverted

### Parameters

This function has no parameters.

UI\\Draw\\Matrix::multiply
==========================

Multiply Matrix

### Description

<span class="modifier">public</span> <span
class="type">UI\\Draw\\Matrix</span> <span
class="methodname">UI\\Draw\\Matrix::multiply</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Matrix</span>
`$matrix`</span> )

Shall multiply this matrix with the given matrix

### Parameters

This function has no parameters.

### Return Values

The new Matrix

UI\\Draw\\Matrix::rotate
========================

Rotate Matrix

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Matrix::rotate</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
, <span class="methodparam"><span class="type">float</span>
`$amount`</span> )

Shall rotate this Matrix

### Parameters

`point`  

`amount`  

UI\\Draw\\Matrix::scale
=======================

Scale Matrix

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Matrix::scale</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$center`</span>
, <span class="methodparam"><span class="type">UI\\Point</span>
`$point`</span> )

Shall scale this Matrix

### Parameters

`center`  

`point`  

UI\\Draw\\Matrix::skew
======================

Skew Matrix

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Matrix::skew</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
, <span class="methodparam"><span class="type">UI\\Point</span>
`$amount`</span> )

Shall skew this Matrix

### Parameters

`point`  

`amount`  

UI\\Draw\\Matrix::translate
===========================

Translate Matrix

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Matrix::translate</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$point`</span>
)

Shall translate this Matrix

### Parameters

`point`  

Introduction
------------

Represents RGBA colours, individual channels are accessible via public
properties.

Class synopsis
--------------

**UI\\Draw\\Color**

<span class="ooclass"> class **UI\\Draw\\Color** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Color::Red` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Color::Green` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Color::Blue` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Color::Alpha` ;

/\* Properties \*/

<span class="modifier">public</span> `$r` ;

<span class="modifier">public</span> `$g` ;

<span class="modifier">public</span> `$b` ;

<span class="modifier">public</span> `$a` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$color`</span> \] )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getChannel</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setChannel</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> ,
<span class="methodparam"><span class="type">float</span>
`$value`</span> )

}

Properties
----------

`r`  
Provides access to the red channel

`g`  
Provides access to the green channel

`b`  
Provides access to the blue channel

`a`  
Provides access to the alpha channel

Predefined Constants
--------------------

**`UI\Draw\Color::Red`**  
Identifies the red channel

**`UI\Draw\Color::Green`**  
Identifies the green channel

**`UI\Draw\Color::Blue`**  
Identifies the blue channel

**`UI\Draw\Color::Alpha`**  
Identifies the alpha channel

UI\\Draw\\Color::\_\_construct
==============================

Construct new Color

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Color::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> \] )

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Color::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$color`</span> \] )

Shall construct a new color

### Parameters

`color`  
May be UI\\Draw\\Color or RRGGBBAA

UI\\Draw\\Color::getChannel
===========================

Color Manipulation

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">UI\\Draw\\Color::getChannel</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> )

Shall retrieve the value for a channel

### Parameters

`channel`  
Constant channel identity

### Return Values

The current value of the requested channel

UI\\Draw\\Color::setChannel
===========================

Color Manipulation

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">UI\\Draw\\Color::setChannel</span> ( <span
class="methodparam"><span class="type">int</span> `$channel`</span> ,
<span class="methodparam"><span class="type">float</span>
`$value`</span> )

Shall set the selected channel to the given value

### Parameters

`channel`  
Constant channel identity

`value`  
The new value for the selected channel

### Return Values

Introduction
------------

Holds the configuration for the Pen to perform a stroke

Class synopsis
--------------

**UI\\Draw\\Stroke**

<span class="ooclass"> class **UI\\Draw\\Stroke** </span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$cap`<span
class="initializer"> = UI\\Draw\\Line\\Cap::Flat</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$join`<span
class="initializer"> = UI\\Draw\\Line\\Join::Miter</span></span> \[,
<span class="methodparam"><span class="type">float</span>
`$thickness`<span class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">float</span> `$miterLimit`<span
class="initializer"> = 10</span></span> \]\]\]\] )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getCap</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getJoin</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getMiterLimit</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getThickness</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">setCap</span> ( <span class="methodparam"><span
class="type">int</span> `$cap`</span> )

<span class="modifier">public</span> <span
class="methodname">setJoin</span> ( <span class="methodparam"><span
class="type">int</span> `$join`</span> )

<span class="modifier">public</span> <span
class="methodname">setMiterLimit</span> ( <span
class="methodparam"><span class="type">float</span> `$limit`</span> )

<span class="modifier">public</span> <span
class="methodname">setThickness</span> ( <span class="methodparam"><span
class="type">float</span> `$thickness`</span> )

}

UI\\Draw\\Stroke::\_\_construct
===============================

Construct a new Stroke

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Stroke::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$cap`<span
class="initializer"> = UI\\Draw\\Line\\Cap::Flat</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$join`<span
class="initializer"> = UI\\Draw\\Line\\Join::Miter</span></span> \[,
<span class="methodparam"><span class="type">float</span>
`$thickness`<span class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">float</span> `$miterLimit`<span
class="initializer"> = 10</span></span> \]\]\]\] )

Shall construct a new Stroke

### Parameters

`cap`  
UI\\Draw\\Line\\Cap::Flat, UI\\Draw\\Line\\Cap::Round, or
UI\\Draw\\Line\\Cap::Square

`join`  
UI\\Draw\\Line\\Join::Miter, UI\\Draw\\Line\\Join::Round, or
UI\\Draw\\Line\\Join::Bevel

`thickness`  
The thickness of the stroke

`miterLimit`  
Miter limit (default is sensible for all supported platforms)

UI\\Draw\\Stroke::getCap
========================

Get Line Cap

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Stroke::getCap</span> ( <span
class="methodparam">void</span> )

Shall retrieve the line cap setting of this Stroke

### Parameters

This function has no parameters.

### Return Values

UI\\Draw\\Line\\Cap::Flat, UI\\Draw\\Line\\Cap::Round, or
UI\\Draw\\Line\\Cap::Square

UI\\Draw\\Stroke::getJoin
=========================

Get Line Join

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Stroke::getJoin</span> ( <span
class="methodparam">void</span> )

Shall retrieve the line join setting of this Stroke

### Parameters

This function has no parameters.

### Return Values

UI\\Draw\\Line\\Join::Miter, UI\\Draw\\Line\\Join::Round, or
UI\\Draw\\Line\\Join::Bevel

UI\\Draw\\Stroke::getMiterLimit
===============================

Get Miter Limit

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">UI\\Draw\\Stroke::getMiterLimit</span> ( <span
class="methodparam">void</span> )

Shall retrieve the miter limit of this Stroke

### Parameters

This function has no parameters.

### Return Values

The current miter limit

UI\\Draw\\Stroke::getThickness
==============================

Get Thickness

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">UI\\Draw\\Stroke::getThickness</span> ( <span
class="methodparam">void</span> )

Shall retrieve the thickness of this Stroke

### Parameters

This function has no parameters.

### Return Values

The current thickness

UI\\Draw\\Stroke::setCap
========================

Set Line Cap

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Stroke::setCap</span> ( <span
class="methodparam"><span class="type">int</span> `$cap`</span> )

Shall set the line cap setting for this Stroke

### Parameters

`cap`  
UI\\Draw\\Line\\Cap::Flat, UI\\Draw\\Line\\Cap::Round, or
UI\\Draw\\Line\\Cap::Square

UI\\Draw\\Stroke::setJoin
=========================

Set Line Join

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Stroke::setJoin</span> ( <span
class="methodparam"><span class="type">int</span> `$join`</span> )

Shall set the line join setting for this Stroke

### Parameters

`join`  
UI\\Draw\\Line\\Join::Miter, UI\\Draw\\Line\\Join::Round, or
UI\\Draw\\Line\\Join::Bevel

### Return Values

UI\\Draw\\Stroke::setMiterLimit
===============================

Set Miter Limit

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Stroke::setMiterLimit</span> ( <span
class="methodparam"><span class="type">float</span> `$limit`</span> )

Set the miter limit for this Stroke

### Parameters

`limit`  
The new limit

UI\\Draw\\Stroke::setThickness
==============================

Set Thickness

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Stroke::setThickness</span> ( <span
class="methodparam"><span class="type">float</span> `$thickness`</span>
)

Shall set the thickness for this Stroke

### Parameters

`thickness`  
The new thickness

Introduction
------------

Represents a solid color brush

Class synopsis
--------------

**UI\\Draw\\Brush**

<span class="ooclass"> class **UI\\Draw\\Brush** </span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span
class="type">UI\\Draw\\Color</span> <span
class="methodname">getColor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setColor</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setColor</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> )

}

UI\\Draw\\Brush::\_\_construct
==============================

Construct a new Brush

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Brush::\_\_construct</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> )

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Brush::\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> )

Shall construct a solid brush using the given color

### Parameters

`color`  
Can be a UI\\Draw\\Color or RRGGBBAA

UI\\Draw\\Brush::getColor
=========================

Get Color

### Description

<span class="modifier">public</span> <span
class="type">UI\\Draw\\Color</span> <span
class="methodname">UI\\Draw\\Brush::getColor</span> ( <span
class="methodparam">void</span> )

Shall return a UI\\Draw\\Color for this brush

### Parameters

This function has no parameters.

### Return Values

The current color of the brush

UI\\Draw\\Brush::setColor
=========================

Set Color

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">UI\\Draw\\Brush::setColor</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">UI\\Draw\\Brush::setColor</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> )

Shall set the color of this brush to the color provided

### Parameters

`color`  
Can be a UI\\Draw\\Color or RRGGBBAA

### Return Values

Introduction
------------

Abstract for gradient brushes

Class synopsis
--------------

**UI\\Draw\\Brush\\Gradient**

<span class="ooclass"> <span class="modifier">abstract</span> class
**UI\\Draw\\Brush\\Gradient** </span> <span class="ooclass"> <span
class="modifier">extends</span> **UI\\Draw\\Brush** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">addStop</span> ( <span class="methodparam"><span
class="type">float</span> `$position`</span> , <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">addStop</span> ( <span class="methodparam"><span
class="type">float</span> `$position`</span> , <span
class="methodparam"><span class="type">int</span> `$color`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">delStop</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStop</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">float</span>
`$position`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Color</span> `$color`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setStop</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">float</span>
`$position`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">UI\\Draw\\Color</span> <span
class="methodname">UI\\Draw\\Brush::getColor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">UI\\Draw\\Brush::setColor</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">UI\\Draw\\Brush::setColor</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> )

}

UI\\Draw\\Brush\\Gradient::addStop
==================================

Stop Manipulation

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Brush\\Gradient::addStop</span> ( <span
class="methodparam"><span class="type">float</span> `$position`</span> ,
<span class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Brush\\Gradient::addStop</span> ( <span
class="methodparam"><span class="type">float</span> `$position`</span> ,
<span class="methodparam"><span class="type">int</span> `$color`</span>
)

Shall at a stop of the given color at the given position

### Parameters

`position`  
The position for the new stop

`color`  
The color for the new stop, may be UI\\Draw\\Color or RRGGBBAA

### Return Values

Total number of stops

UI\\Draw\\Brush\\Gradient::delStop
==================================

Stop Manipulation

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Brush\\Gradient::delStop</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`index`  

### Return Values

Total number of stops

UI\\Draw\\Brush\\Gradient::setStop
==================================

Stop Manipulation

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Draw\\Brush\\Gradient::setStop</span> (
<span class="methodparam"><span class="type">int</span> `$index`</span>
, <span class="methodparam"><span class="type">float</span>
`$position`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Color</span> `$color`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Draw\\Brush\\Gradient::setStop</span> (
<span class="methodparam"><span class="type">int</span> `$index`</span>
, <span class="methodparam"><span class="type">float</span>
`$position`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> )

### Parameters

`index`  
The index of the stop to set

`position`  
The position for the stop

`color`  
The color for the stop, may be UI\\Draw\\Color or RRGGBBAA

### Return Values

Indication of success

Introduction
------------

Class synopsis
--------------

**UI\\Draw\\Brush\\LinearGradient**

<span class="ooclass"> class **UI\\Draw\\Brush\\LinearGradient** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**UI\\Draw\\Brush\\Gradient** </span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$start`</span>
, <span class="methodparam"><span class="type">UI\\Point</span>
`$end`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Brush\\Gradient::addStop</span> ( <span
class="methodparam"><span class="type">float</span> `$position`</span> ,
<span class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Brush\\Gradient::addStop</span> ( <span
class="methodparam"><span class="type">float</span> `$position`</span> ,
<span class="methodparam"><span class="type">int</span> `$color`</span>
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Brush\\Gradient::delStop</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Draw\\Brush\\Gradient::setStop</span> (
<span class="methodparam"><span class="type">int</span> `$index`</span>
, <span class="methodparam"><span class="type">float</span>
`$position`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Color</span> `$color`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Draw\\Brush\\Gradient::setStop</span> (
<span class="methodparam"><span class="type">int</span> `$index`</span>
, <span class="methodparam"><span class="type">float</span>
`$position`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> )

}

UI\\Draw\\Brush\\LinearGradient::\_\_construct
==============================================

Construct a Linear Gradient

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Brush\\LinearGradient::\_\_construct</span>
( <span class="methodparam"><span class="type">UI\\Point</span>
`$start`</span> , <span class="methodparam"><span
class="type">UI\\Point</span> `$end`</span> )

Shall construct a new linear gradient

### Parameters

`start`  

`end`  

Introduction
------------

Class synopsis
--------------

**UI\\Draw\\Brush\\RadialGradient**

<span class="ooclass"> class **UI\\Draw\\Brush\\RadialGradient** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**UI\\Draw\\Brush\\Gradient** </span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">UI\\Point</span> `$start`</span>
, <span class="methodparam"><span class="type">UI\\Point</span>
`$outer`</span> , <span class="methodparam"><span
class="type">float</span> `$radius`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Brush\\Gradient::addStop</span> ( <span
class="methodparam"><span class="type">float</span> `$position`</span> ,
<span class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Brush\\Gradient::addStop</span> ( <span
class="methodparam"><span class="type">float</span> `$position`</span> ,
<span class="methodparam"><span class="type">int</span> `$color`</span>
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Brush\\Gradient::delStop</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Draw\\Brush\\Gradient::setStop</span> (
<span class="methodparam"><span class="type">int</span> `$index`</span>
, <span class="methodparam"><span class="type">float</span>
`$position`</span> , <span class="methodparam"><span
class="type">UI\\Draw\\Color</span> `$color`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">UI\\Draw\\Brush\\Gradient::setStop</span> (
<span class="methodparam"><span class="type">int</span> `$index`</span>
, <span class="methodparam"><span class="type">float</span>
`$position`</span> , <span class="methodparam"><span
class="type">int</span> `$color`</span> )

}

UI\\Draw\\Brush\\RadialGradient::\_\_construct
==============================================

Construct a new Radial Gradient

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Brush\\RadialGradient::\_\_construct</span>
( <span class="methodparam"><span class="type">UI\\Point</span>
`$start`</span> , <span class="methodparam"><span
class="type">UI\\Point</span> `$outer`</span> , <span
class="methodparam"><span class="type">float</span> `$radius`</span> )

Shall construct a new radial gradient

### Parameters

`start`  

`outer`  

`radius`  

Introduction
------------

A Text Layout represents the layout of text which will be drawn by the
Pen

Class synopsis
--------------

**UI\\Draw\\Text\\Layout**

<span class="ooclass"> class **UI\\Draw\\Text\\Layout** </span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> ,
<span class="methodparam"><span class="type">UI\\Draw\\Text\\Font</span>
`$font`</span> , <span class="methodparam"><span
class="type">float</span> `$width`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">setColor</span> ( <span class="methodparam"><span
class="type">UI\\Draw\\Color</span> `$color`</span> \[, <span
class="methodparam"><span class="type">int</span> `$start`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$end`</span> \]\] )

<span class="modifier">public</span> <span
class="methodname">setColor</span> ( <span class="methodparam"><span
class="type">int</span> `$color`</span> \[, <span
class="methodparam"><span class="type">int</span> `$start`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$end`</span> \]\] )

<span class="modifier">public</span> <span
class="methodname">setWidth</span> ( <span class="methodparam"><span
class="type">float</span> `$width`</span> )

}

UI\\Draw\\Text\\Layout::\_\_construct
=====================================

Construct a new Text Layout

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Text\\Layout::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> ,
<span class="methodparam"><span class="type">UI\\Draw\\Text\\Font</span>
`$font`</span> , <span class="methodparam"><span
class="type">float</span> `$width`</span> )

Shall construct a new Text Layout

### Parameters

`text`  
The text for the layout

`font`  
The font to use for writing

`width`  
The width of the layout

UI\\Draw\\Text\\Layout::setColor
================================

Set Color

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Text\\Layout::setColor</span> ( <span
class="methodparam"><span class="type">UI\\Draw\\Color</span>
`$color`</span> \[, <span class="methodparam"><span
class="type">int</span> `$start`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$end`</span> \]\] )

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Text\\Layout::setColor</span> ( <span
class="methodparam"><span class="type">int</span> `$color`</span> \[,
<span class="methodparam"><span class="type">int</span> `$start`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$end`</span> \]\] )

Shall set the Color for all of, or a range of the text in the Layout

### Parameters

`color`  
The color to use

`start`  
The starting character

`end`  
The ending character, by default the end of the string

UI\\Draw\\Text\\Layout::setWidth
================================

Set Width

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Text\\Layout::setWidth</span> ( <span
class="methodparam"><span class="type">float</span> `$width`</span> )

Shall set the width of this Text Layout

### Parameters

`width`  
The new width

Introduction
------------

Loads a described font

Class synopsis
--------------

**UI\\Draw\\Text\\Font**

<span class="ooclass"> class **UI\\Draw\\Text\\Font** </span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span
class="type">UI\\Draw\\Text\\Font\\Descriptor</span>
`$descriptor`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getAscent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getDescent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getLeading</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getUnderlinePosition</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getUnderlineThickness</span> ( <span
class="methodparam">void</span> )

}

UI\\Draw\\Text\\Font::\_\_construct
===================================

Construct a new Font

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Text\\Font::\_\_construct</span> ( <span
class="methodparam"><span
class="type">UI\\Draw\\Text\\Font\\Descriptor</span>
`$descriptor`</span> )

Shall construct a new Font using the given descriptor

### Parameters

`descriptor`  
The descriptor for the Font

UI\\Draw\\Text\\Font::getAscent
===============================

Font Metrics

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">UI\\Draw\\Text\\Font::getAscent</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

UI\\Draw\\Text\\Font::getDescent
================================

Font Metrics

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">UI\\Draw\\Text\\Font::getDescent</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

UI\\Draw\\Text\\Font::getLeading
================================

Font Metrics

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">UI\\Draw\\Text\\Font::getLeading</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

UI\\Draw\\Text\\Font::getUnderlinePosition
==========================================

Font Metrics

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span
class="methodname">UI\\Draw\\Text\\Font::getUnderlinePosition</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

UI\\Draw\\Text\\Font::getUnderlineThickness
===========================================

Font Metrics

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span
class="methodname">UI\\Draw\\Text\\Font::getUnderlineThickness</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

Describes a font

Class synopsis
--------------

**UI\\Draw\\Text\\Font\\Descriptor**

<span class="ooclass"> class **UI\\Draw\\Text\\Font\\Descriptor**
</span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$family`</span> ,
<span class="methodparam"><span class="type">float</span> `$size`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$weight`<span class="initializer"> =
UI\\Draw\\Text\\Font\\Weight::Normal</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$italic`<span
class="initializer"> =
UI\\Draw\\Text\\Font\\Italic::Normal</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$stretch`<span
class="initializer"> =
UI\\Draw\\Text\\Font\\Stretch::Normal</span></span> \]\]\] )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFamily</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getItalic</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">float</span>
<span class="methodname">getSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getStretch</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getWeight</span> ( <span
class="methodparam">void</span> )

}

UI\\Draw\\Text\\Font\\Descriptor::\_\_construct
===============================================

Construct a new Font Descriptor

### Description

<span class="modifier">public</span> <span
class="methodname">UI\\Draw\\Text\\Font\\Descriptor::\_\_construct</span>
( <span class="methodparam"><span class="type">string</span>
`$family`</span> , <span class="methodparam"><span
class="type">float</span> `$size`</span> \[, <span
class="methodparam"><span class="type">int</span> `$weight`<span
class="initializer"> =
UI\\Draw\\Text\\Font\\Weight::Normal</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$italic`<span
class="initializer"> =
UI\\Draw\\Text\\Font\\Italic::Normal</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$stretch`<span
class="initializer"> =
UI\\Draw\\Text\\Font\\Stretch::Normal</span></span> \]\]\] )

Shall construct a new Font Descriptor

### Parameters

`family`  
The name of a valid family of fonts

`size`  
The preferred size

`weight`  
UI\\Draw\\Text\\Font\\Weight constant

`italic`  
UI\\Draw\\Text\\Font\\Italic constant

`stretch`  
UI\\Draw\\Text\\Font\\Stretch constant

UI\\Draw\\Text\\Font\\Descriptor::getFamily
===========================================

Get Font Family

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span
class="methodname">UI\\Draw\\Text\\Font\\Descriptor::getFamily</span> (
<span class="methodparam">void</span> )

Shall return the requested font family

### Parameters

This function has no parameters.

### Return Values

UI\\Draw\\Text\\Font\\Descriptor::getItalic
===========================================

Style Detection

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Text\\Font\\Descriptor::getItalic</span> (
<span class="methodparam">void</span> )

Shall return constant setting

### Parameters

This function has no parameters.

### Return Values

UI\\Draw\\Text\\Font\\Descriptor::getSize
=========================================

Size Detection

### Description

<span class="modifier">public</span> <span class="type">float</span>
<span
class="methodname">UI\\Draw\\Text\\Font\\Descriptor::getSize</span> (
<span class="methodparam">void</span> )

Shall return the requested size

### Parameters

This function has no parameters.

### Return Values

UI\\Draw\\Text\\Font\\Descriptor::getStretch
============================================

Style Detection

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Text\\Font\\Descriptor::getStretch</span> (
<span class="methodparam">void</span> )

Shall return requested stretch

### Parameters

This function has no parameters.

### Return Values

UI\\Draw\\Text\\Font\\Descriptor::getWeight
===========================================

Weight Detection

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">UI\\Draw\\Text\\Font\\Descriptor::getWeight</span> (
<span class="methodparam">void</span> )

Shall return requested weight

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

Class synopsis
--------------

**UI\\Draw\\Text\\Font\\Weight**

<span class="ooclass"> <span class="modifier">final</span> class
**UI\\Draw\\Text\\Font\\Weight** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::Thin` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::UltraLight` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::Light` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::Book` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::Normal` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::Medium` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::SemiBold` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::Bold` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::UltraBold` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::Heavy` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Weight::UltraHeavy` ;

}

Introduction
------------

Class synopsis
--------------

**UI\\Draw\\Text\\Font\\Italic**

<span class="ooclass"> <span class="modifier">final</span> class
**UI\\Draw\\Text\\Font\\Italic** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Italic::Normal` <span class="initializer"> = 0</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Italic::Oblique` <span class="initializer"> =
1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Italic::Italic` <span class="initializer"> = 2</span>
;

}

Introduction
------------

Class synopsis
--------------

**UI\\Draw\\Text\\Font\\Stretch**

<span class="ooclass"> <span class="modifier">final</span> class
**UI\\Draw\\Text\\Font\\Stretch** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Stretch::UltraCondensed` <span class="initializer"> =
0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Stretch::ExtraCondensed` <span class="initializer"> =
1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Stretch::Condensed` <span class="initializer"> =
2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Stretch::SemiCondensed` <span class="initializer"> =
3</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Stretch::Normal` <span class="initializer"> =
4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Stretch::SemiExpanded` <span class="initializer"> =
5</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Stretch::Expanded` <span class="initializer"> =
6</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Stretch::ExtraExpanded` <span class="initializer"> =
7</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Text\Font\Stretch::UltraExpanded` <span class="initializer"> =
8</span> ;

}

Introduction
------------

Class synopsis
--------------

**UI\\Draw\\Line\\Cap**

<span class="ooclass"> <span class="modifier">final</span> class
**UI\\Draw\\Line\\Cap** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Line\Cap::Flat` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Line\Cap::Round` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Line\Cap::Square` ;

}

Introduction
------------

Class synopsis
--------------

**UI\\Draw\\Line\\Join**

<span class="ooclass"> <span class="modifier">final</span> class
**UI\\Draw\\Line\\Join** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Line\Join::Miter` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Line\Join::Round` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Draw\Line\Join::Bevel` ;

}

Introduction
------------

Class synopsis
--------------

**UI\\Key**

<span class="ooclass"> <span class="modifier">final</span> class
**UI\\Key** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::Escape` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::Insert` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::Delete` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::Home` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::End` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::PageUp` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::PageDown` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::Up` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::Down` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::Left` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::Right` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F1` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F2` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F3` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F4` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F5` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F6` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F7` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F8` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F9` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F10` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F11` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::F12` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::N0` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::N1` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::N2` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::N3` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::N4` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::N5` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::N6` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::N7` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::N8` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::N9` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::NDot` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::NEnter` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::NAdd` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::NSubtract` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::NMultiply` ;

<span class="modifier">const</span> <span class="type">int</span>
`UI\Key::NDivide` ;

}

Introduction
------------

Class synopsis
--------------

**UI\\Exception\\InvalidArgumentException**

<span class="ooclass"> class **UI\\Exception\\InvalidArgumentException**
</span> <span class="ooclass"> <span class="modifier">extends</span>
**InvalidArgumentException** </span> <span
class="oointerface">implements <span
class="interfacename">Throwable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Class synopsis
--------------

**UI\\Exception\\RuntimeException**

<span class="ooclass"> class **UI\\Exception\\RuntimeException** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**RuntimeException** </span> <span class="oointerface">implements <span
class="interfacename">Throwable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}
