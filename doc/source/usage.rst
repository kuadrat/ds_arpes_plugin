Usage
=====

To load the plugin, run the following command inn the ipython console of PIT:: 

   arpes = mw.load_plugin('ds_arpes_plugin')

(Of course you can use any variable name of your choice instead of ``arpes``, 
but be aware that if you set up PIT to autoload this plugin, it will be 
available as ``arpes``).

You are now able to load ARPES data into PIT by doing::

   arpes.open('<filename>')

Of course, this requires a respective dataloader for the dataset you're 
trying to load to exist.

After loading, the usual ``D`` namespace is available as ``arpes.D``, so you 
can, for example, access the data as ``arpes.D.data``.
Of course, at the same time PIT holds the data in its usual location and can 
be accessed by ``pit.get_data()``.

If the data isn't displayed the way you'd expect, try a 
:func:`~data_slicer.pit.PIT_DataHandler.roll_axes`.

.. Note::
   
   Datasets that represent single ARPES spectra (i.e. 2D data) are still 
   loaded by ``arpys`` as 3D arrays where one dimension has length 1.
   Somehow, this causes buggy behaviour in PIT and not all functionality may 
   be available.

Basically, ``ds_arpes_plugin`` provides you all the tools of the `arpys 
module <https://github.com/kuadrat/arpys>`_ through the ``arpes.pp`` and 
``arpes.dl`` instances.
Additionally, some convenience methods exist, most notably :func:`arpes.a2k 
<ds_arpes_plugin.ds_arpes_plugin.ARPES_Plugin.a2k>` for convenient angle to k 
space conversion.
Check the :ref:`full code reference <section-api>` for more.
