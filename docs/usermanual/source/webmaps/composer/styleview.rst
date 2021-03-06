.. _webmaps.composer.styleview:

Viewing and styling maps and layers
===================================

Once layers and maps have been published and created, the next step is to view and style them appropriately. Composer makes this easy by offering a single editing environment where layers can be viewed, styles edited, and the view refreshed, all without leaving the page.

Accessing the Style Editor
--------------------------

The Style Editor can be accessed for a single layer or for a map.

To view a single layer, select the layer in the appropriate :ref:`webmaps.composer.configuration` page and then click :guilabel:`Style`.

.. figure:: img/layerstylelink.png

   Link to view/style a layer

To view a map, navigate to the map in the appropriate :ref:`webmaps.composer.configuration` page and click the preview image.

.. figure:: img/mapstylelink.png

   Link to view/style a map

Style Editor
------------

The Style Editor is mostly the same whether styling a layer or a map. The only difference is the existence of the layer list in the middle of the screen.

.. figure:: img/mapstylepage.png

   Styling a map

.. figure:: img/layerstylepage.png

   Styling a single layer

The Style Editor page consists of two (or three) panels.

* The **viewer** on the left side shows the current style of layer or map. In this panel there are buttons for zoom in/out, zoom to extent, and copy bounds. There is also the current scale and zoom level.
* For maps only, there is a **layer list**. This list can be dragged to adjust drawing order, and each layer can be toggled on or off in visibility (without removing them from the map).
* The **style** panel shows the current style for the selected layer. Even if viewing a map, only one layer's style will be shown at once. 

.. todo:: Names are made up.

Style toolbar
~~~~~~~~~~~~~

On the style panel there is a toolbar with the following buttons:

.. list-table::
   :class: non-responsive
   :header-rows: 1
   :stub-columns: 1

   * - Button
     - Description
   * - :guilabel:`Layers`
     - Shows/hides the layers panel. Only valid when viewing a map.
   * - :guilabel:`Save`
     - Saves the current style
   * - :guilabel:`Font`
     - Changes the display font for the style. Options are system dependent. **Only affects how the style code is viewed, not the style itself.**
   * - :guilabel:`Size`
     - Change sthe size of the display font for the style. Options are :guilabel:`Small`, :guilabel:`Smaller`, :guilabel:`Normal`, :guilabel:`Larger`, and :guilabel:`Large`  **Only affects how the style code is viewed,  not the style itself.**
   * - :guilabel:`Color`
     - Allows a color to be chosen from a color picker and subsequently inserted into the style.
   * - :guilabel:`Icons`
     - Allows for icons (graphics) to be chosen and inserted into a style. Icons can be uploaded from this dialog as well. See the section on :ref:`webmaps.composer.styleview.icons`.
   * - :guilabel:`Undo`
     - Returns to a previous version of the style
   * - :guilabel:`Attributes`
     - Shows a list of the available attributes. Useful when creating :ref:`style filters <cartography.ysld.reference.filters>`.

Editing styles
~~~~~~~~~~~~~~

Styles are written in the YSLD markup language, which is compatible with but simpler than SLD. For more information about YSLD syntax, please see the section on :ref:`cartography.ysld`.

.. _webmaps.composer.styleview.icons:

Using icons in a style
~~~~~~~~~~~~~~~~~~~~~~

Composer has the ability to upload icons and other graphics and associate them with a given layer's style.

To upload an image file to be used as a graphic in a style:

#. In the style toolbar, click :guilabel:`Icons`.

   .. figure:: img/icons_button.png

      Icons button in the style toolbar

#. A list of the avilable icons in that project workspace will be shown, if any.

   .. figure:: img/icons_list.png

      No icons available in the project workspace

#. Click :guilabel:`Upload icon`.

#. A file chooser will display. Select the file on your system to be uploaded.

#. The file will then be displayed in the list.

   .. figure:: img/icons_new.png

      Newly uploaded icon available

#. To add this icon to the current style, select the icon and then click :guilabel:`Copy selected to Clipboard`.

#. The dialog will close automatically. Paste the path in the appropriate location, such as:

   .. code-block:: yaml
      :emphasize-lines: 2

      - external:
          url: /workspaces/tutorial/styles/smileyface.png
          format: image/png

   .. note:: The pasted code will be of the form ``/workspaces/<project_workspace>/styles/<filename.ext>``.

   .. figure:: img/icons_pasted.png

      Icon location added to style

.. note:: All web-friendly file formats are supported through this interface.

