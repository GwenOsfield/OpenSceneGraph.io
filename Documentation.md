Getting Started

Follows is a quick step by step guide to helping new OpenSceneGraph users get up to speed on how to use the software in their own application development work.

1. Downloading the OpenSceneGraph
You may download the OpenSceneGraph as a set of binaries or source code tarballs for the current release which can be found on the Stable Releases section, or use the Code Repositories or Developer Releases to check out the development version of the OpenSceneGraph to get latest additions, revisions and bug fixes. For beginners we'd recommend using the binaries or the source tarballs.

2. Obtaining the pre-requisites tools/dependencies
If you plan to compile the OpenSceneGraph you'll also need to the build system generator tool CMake 2.6.x (CMake 2.4.2+ may be used on older Linux/Unix systems) and an appropriate compiler suite for your platform, i.e. VisualStudio, g++ etc. For modern linux distributions you'll be able to pull down cmake, g++ and other dependencies directly from central repositories. It's possible to compile in mac using clang or Xcode.

You will need to download the dependencies which are listed in the Dependencies section. You don't need all the dependencies for the plugins as this are all options libraries, so don't worry about trying to get all the dependencies installed, you can always add further dependencies later if it turns out you need them for your project.

When running the examples its is useful to install the Sample Dataset so that the examples have some data to load, download it.

3. Compiling
OpenSceneGraph is a multiplatform library so take a look to platform specifics section to know how to compile in your desired platform or with your favorite compiler.

4. Running the examples 
OpenSceneGraph has an ever growing number of examples available for developers to learn from. Follow the Running Examples Guide to experiment and learn with them.

5. Write your first application
Take one of the existing examples such as osgviewer as a base and modify it.

6. Debugging
Make use of the Debugging Tips to learn how to debug your application.

7. Further resources
Books - Books to learn how to use OpenSceneGraph
Programming Guides - programming with OpenSceneGraph
Reference Guides - OpenSceneGraph API reference documentation
User Guides - Applications and examples user guides
FAQ - Frequently Asked Questions
Tutorials - programming tutorials/howtos.
Tips And Tricks - quick snippets of informtation that can help you along
Knowledge Base - Useful background knowledge

Books and Guides

links - quick start guide
- beginners guide
- cookbook

This section aims to supply user, programming and reference guides to the OpenSceneGraph developers community.

Reference Guides 
User Guides 
The user guide section provides details to users on how to use various applications associated with OpenSceneGraph, such as standard viewers, and data processing and conversion tools.

Programming Guides 
On line programming guides on the concepts and usage of OpenSceneGraph.

FAQ's
Here is a list of Frequently Asked Questions.

More FAQs about OSG may be found at 3drealtimesimulation.

General
I have no idea what OpenSceneGraph is, can you give me a short description?
It is a 3D graphics library for C++ programmers. A SceneGraph library allows you to represent objects in a scene with a graph data structure which allows you to group related objects that share some properties together so you can specify common properties for the whole group in one place. OpenSceneGraph can then be used to automatically manage things like the level of detail necessary to draw the scene faithfully but without unnecessary detail which slows down the graphics hardware drawing the scene.

What platforms does the OpenSceneGraph support?
Microsoft Windows (2000, XP, Vista), GNU/Linux and MacOS/X are currently the best supported ones. Your mileage may vary on Solaris, IRIX, ...

What renderers (OpenGL, DirectX, ...) does the OpenSceneGraph support?
OpenSceneGraph only supports rendering through OpenGL. In fact, a lot of the classes in the library are merely object-oriented versions of OpenGL concepts.

Where can I get more info on OpenSceneGraph?
Try these:

Look at the official homepage at http://www.openscenegraph.org/ (this FAQ is located there)
Join the mailing lists, specifically "osg-users". See MailingLists for more information.
What background knowledge is required/useful if I want to work with the OpenSceneGraph?
As the OSG is written in C++ you'll need to be able to program in that language.

One way to look at the OSG is to treat it as an object-oriented wrapper around OpenGL. This is actually a far too simplistic view, as the OSG does a lot more than just issue OpenGL commands for you. However, it does indicate the need to have to knowledge of how OpenGL works in order to use the OpenSceneGraph in a sensible way. Anything you therefore know about OpenGL will be of value when using the OSG. A lot of questions from people just starting out with OpenSceneGraph are actually questions about the basics of OpenGL.

Other topics that are of interest to newcomers to OSG are:

Memory management through reference counting. See the relevant question below, under "Development General".
The use of design patterns, such as Visitor and Observer.
For those already familiar with (real-time) 3D rendering, but not OSG, some features turn out to be common pitfalls:

By default, the OpenSceneGraph manages the clipping planes automatically, to fully use the precision of the Z-buffer. This means that any attempts to set near/far clip values by hand fail, as the values will be overridden.
By default, the OpenSceneGraph uses small-feature culling, meaning that when an object becomes very small in the current view (roughly a few pixels) it will be culled.
The matrices in OSG assume a *pre-multiply* order for vectors, e.g. v' = v * M1 * M2. This is noticeably different from most descriptions in Computer Graphics text books.
What is the difference between OpenSceneGraph and OpenSG?
They are different scenegraph libraries, although OpenSG also seems to use an "OSG" prefix in their code, which might be source of some confusion. Differences in goals and capabilities between the two are:

OpenSceneGraph has support for reading many 3D and image file formats, while OpenSG supports far fewer
OpenSceneGraph is more actively developed (at least, judging by the number of releases of OpenSG) and probably has a more active user community
OpenSG has better support for performing multi-threaded scene graph operations, as this was one of the original design goals
OpenSG has better support for clustered rendering, although building your own support for OpenSceneGraph isn't terribly difficult
The OpenSG website also provides a comparison between the two: http://opensg.vrsource.org/trac/wiki/OSGComparison

Documentation
Are there any books available about OSG?
Yes, see http://www.osgbooks.com.

The books are constantly under revision to keep up with changes in OSG. Purchasing the books helps fund this effort. More OSG books, not just revisions, are planned for the future.

Are there tutorials available?
Yes, see here.

Where is the reference manual for the .osg file format?
There is no documentation (yet) for the scene description language. The OSG source code is the definite reference on the format (UseTheSourceLuke!), specifically the files under the src/osgPlugins/osg directory in the source distribution.

For anyone with knowledge of OpenGL and the OSG classes the .osg format should be fairly understandable, though.

Website
How can I edit a website page?
This website requires a login (See Login). Note that some pages can only be edited by the administrator. This includes the main page, project news and all pages in the Downloads section.

How can I add a new website-page?
One can add a new page by first creating a new article. This can be done in the submit article menu key. You should follow the Author guidelines.

Building/Installation
Are there binary distributions available?
Yes, but only for Windows. For Linux you will have to build OSG yourself or check if your Linux distribution has packages for OSG. On Mac OS/X you will have to build OSG yourself.

I'm not using MS Visual Studio. Does OpenSceneGraph support other Compilers, like mingw32?
There is a build in the distribution for Cygwin and Mingw, but they are primarily supported by folks on the osg-users mailing list.

Help! VisualStudio won't load the OSG project files
If you're getting the message "This makefile was not generated by Developer Studio", then the .dsp files were somehow saved with Unix style endlines. You can fix this any number of ways. Suggestions include: Open and Save the .dsp in Wordpad, use the cygwin utility unix2dos, or open the daily tarball in Winzip (after checking "TAR File Smart CR/LF conversion" in Options->Configuration->Miscellaneous).

Everything is compiled, but there are linking problems OR when I run my OSG application it crashes
On Linux, try a "make clean", then "make". On Windows do a clean build. This problem is sometimes caused by a change in the api or a project setting/library has been changed. Doing a clean recompile of everything from scratch can fix the problem.

Linking errors are also often caused by omitting libraries in Visual Studio. Go to Project->Settings and under the Link tab check to see that for every .dll you want to use, the equivalent .lib file is listed under "Object/library Modules" For example, in order to link to the core debug library osgd.dll, osgd.lib should be listed. The search path for these libraries is under Tools->Options->Directories.

On Linux you may need to add an entry to /etc/ld.so.conf.d/ and run ldconfig, or set your LD_LIBRARY_PATH to include the location where you installed the OSG libraries.

Functionality/Features
Where is the camera class for OpenSceneGraph?
The core OpenSceneGraph library provides an osg::Camera class that provides various controls capturing pictures of the scene, be it as part of viewer or as part of the scene graph when doing render to texture effects such shadows, reflections etc. The osg::Camera class is defined in OpenSceneGraph/include/osg/Camera.

How do I render terrain in OSG?
The OpenSceneGraph now has the osgTerrain NodeKit for rendering terrain, and multi-threaded paging system that can be used independently or together for rendering of large terrain databases. The companion project VirtualPlanetBuilder can be used to build large scale paged databases, including Terra-byte scale whole earth geospatial databases, outputting directly in native OpenSceneGraph binary formats.

If you wish to use a continuous level of details approach to terrain see Demeter (http://www.terrainengine.com/) and the Virtual Terrain Project (http://www.vterrain.org/) for detailed open source approaches.

I can't get GLUT working OR GLUT doesn't provide feature X
You're better off using wxWidgets (http://www.wxwidgets.org/) or Simple Direct Media Layer (http://www.libsdl.org/). Both are OpenSource and provide the OpenGL renderpanes for OSG to work on.

Is there support for skeletal animation?
Check out osgCal which integrates the OSG with Cal3D, see http://osgcal.sourceforge.net/

What file formats are supported by OpenSceneGraph?
File input and output is supported through the plugins in the src/osgPlugins directory of the source distribution. See Support/UserGuides/Plugins for an overview of available plugins, the file formats they support and the read/write capabilities of the plugins.

Note that some of the plugins depend on external libraries to be installed! A very frequent question from people just starting out using the OSG is why a certain plugin (such as for reading JPEG images) is not available. Most of the time missing plugins are caused by not having the correct information on dependencies during building of the OSG. The CMake build tool needs to know the location of plugin dependency headers and libraries, such as libjpeg, libtiff, GDAL, etc. Especially on Windows, where libraries do not have standard locations in the file system.

Some additional file formats are also supported by the Virtual Terrain Project (http://www.vterrain.org/). (Wiki editing note: what does this remark have to do with OpenSceneGraph?)

Does the OpenSceneGraph have a native file format?
From OpenSceneGraph-3.0 onwards we have new native file formats based on generic serializers that are extensible and support forward/backward compatibility, there is a .osgt ascii text file format, .osgx xml format and .osgb binary format. The extensible of the new formats enables end user application to add serializer wrappers for their own classes enabling them to extend the formats for their own application needs.

Prior to OpenSceneGraph-3.0 there were two native file formats, .osg for ascii, and .ive for binary. The .osg format is extensible and flexible but is slower and less compact than the .ive binary format, but the later suffers from not being forwards compatible and is not extensible so is only suitable for scene graphs that aren't extended by end user applications.

(Wiki editing note: is this correct about the .ive format?)

Are there sample files that OSG can read for me to play with?
Yes, there is a sample dataset. Actually, some of the examples included in the OSG distribution depend on having them installed. See Downloads/SampleDatasets.

Can I use OpenGL commands directly in OSG ?
Yes. See, for example, the osgteapot example included in the source distribution.

Is it possible to render a scene in 2D?
For a code sample have a look at examples/osghud/osghud.cpp. This example creates a subgraph for viewing a 3D scene, and a second subgraph which sits along side it with osg::Projection & osg::MatrixTransform nodes to set up the orthographic views for drawing the 2D scene over the 3D one.

How do I move models around once they are in the scene?
Add the Node in question to an osg::Transform (as a child). This allows you to move your model around the scene by changing the Transform. Take a look at the osgreflect example, which uses an osg::MatrixTransform? to create a mirror image of a model.

Qt and other GUI frameworks have adapters available in the contribs. Is there one for Gnome/GTK+?
Take a look into the OSGEdit sources (http://www.sf.net/projects/osgedit). It contains a GTK Event Adaptor (a C++ class implemented within the OSGEdit application source code that adapts events from GTK+ to the osgGA generic event framework).

How do I insert comments in a .osg file? OR how do I comment out a block within a .osg file?
Due to the nature of the .osg parser, which allows extensions, one can simply insert a comment in a .osg file by doing this:

Comment {
        This file is proprietary and you shoudn't be reading it.
        Please close your editor now!
        -Microsoft
}
You can also use it to comment out a section of a file:

Comment {
        TexGen {
                UniqueID TexGen_4
                DataVariance? STATIC
                mode SPHERE_MAP=]
        }
}
Development - General
What are these ref_ptr<> things I see everywhere in the code?
The OSG uses reference counting as its basic memory management strategy. All node classes in the scenegraph (subclasses of osg::Node) and a number of other classes as well are derived from osg::Referenced, which holds a reference count (an integer). Instead of directly using pointers to instances osg::ref_ptr<>'s are used, which now how to update the reference count of an osg::Referenced instance based on how many osg::ref_ptr<> point to the instance. The instance is kept alive as long changes in its reference count don't make the count go to zero, meaning that at least one osg::ref_ptr<> is still pointing to the instance. Only when the last osg::ref_ptr<> is removed will the reference count reach zero and will the instance be deleted.

To use osg::ref_ptr<> you basically write

osg::ref_ptr<osg::Group> group = new osg::Group();
// The osg::ref_ptr instance will manage the pointer to the osg::Group
instead of

osg::Group*  group = new osg::Group();
Please see http://andesengineering.com/OSG_ProducerArticles/RefPointers/RefPointers.html for an extensive overview of using ref_ptr's and their particulars.

Why don't the OSG header files have a .h or .hpp extension?
The short answer is that this is the Standard C++ way of naming headers. For more information see these posts on the osg-users mailing list:

http://thread.gmane.org/gmane.comp.graphics.openscenegraph.user/26136

http://osgcvs.no-ip.com/osgarchiver/archives/July2003/0575.html

What can I do to make my editor recognize OSG headers as C++ files?
The means depends upon your editor and platform:

VisualStudio: The OSG source includes a file called VisualStudio_Syntax_Highlighting.txt in the OSG/PlatformSpecifics/Windows directory. Read the instructions there for how to use it.
VIm: can be made to recognize the mode string, "-*-c++-*-", at the beginning of each header file. Start vim. type ":set runtimepath" to see where vim looks for scripts. You can make a file in any of these directories (for example, ~/.vim on Linux). Make the directory if it doesn't already exist, and make a file called scripts.vim in that directory. Here are the contents of that file:
if getline(1) =~ '-*-c++-*-'
set filetype=cpp
endif
Emacs: should recognize the mode string right out of the box.
Nedit: can be told to treat files as C++ based on their location in an include directory
Dev-C++: In Tools/Editor Options/General there is an option "Use Syntax Highlighting". In the box below add ;;. The final line will look like this: c;cpp;h;hpp;;. This will enable syntax highlighting in all files without extension.
How do I increase the verbosity of my program for debugging purposes?
You can use the OSG_NOTIFY_LEVEL environment variable to specify a certain level of debug info. Here are the levels, from low to high (taken from include/osg/Notify):

ALWAYS
FATAL
WARN
NOTICE
INFO
DEBUG_INFO
DEBUG_FP
The default level is NOTICE. Setting OSG_NOTIFY_LEVEL to, for example, INFO will generate more output.

Can I get CVS or Subversion access so I can keep up to date with the latest development sources?
Yes. The OSG sources are available through Subversion. See the documentation on how to set up SVN access to the development version of the OpenSceneGraph.

I don't like using C++. Are there wrappers available for other languages, like Lua?
Yes, see Community/LanguageWrappers. Note that none of these wrappers are part of the official distribution and so are maintained by external parties. They also differ in maturity.

How can I contribute to the OpenSceneGraph?
Send changes as whole files to the osg-submissions mailing list along with an explanation of the changes. Do not send diffs or copy and paste extracts in emails, these will be simply disgarded, as they are too unreliable for review and merging. See MailingLists/SubmissionsProtocol for all the details.

Alternatively you can post changes or submissions under the Community section of this website. This is particularly appropriate for complete new functionality such as NodeKits and plugins. After uploading your things to the website inform the osg-users or osg-submissions list of your entry.

Development - Windows-specific
When I try to save a node to file, OSG crashes. I'm using Windows. OR the STL is playing up for me in VisualStudio (2003/.NET 7).
This is a known problem with the Microsoft implementation of STL. The current solution is to use STLport (http://www.stlport.org/) and make sure you have the latest service pack for VS. If problems persist, make sure you clean your original OpenSceneGraph build and recompile from scratch. The next version of VC++ (dot net, version 7) has a fixed STL implementation, so you won't need STLport after that.

I get a lot of warnings along the lines of... warning C4541: 'dynamic_cast' used on polymorphic type 'class osg::Object' with /GR-
You need to enable run-time type identification. For VisualStudio, you can put /GR in the project options. Or find this option in the development environment, click Settings on the Project menu. Then click the C/C++ tab, and click C++ Language in the Category box. There's a checkbox right there for "Enable RTTI".

How do I embed an OSG viewer in a .NET control?
osgViewer::Viewer* viewer = new osgViewer::Viewer();

HWND hwnd = (HWND)control->Handle.ToPointer();

osg::ref_ptr<osg::GraphicsContext::Traits> traits = new osg::GraphicsContext::Traits();
traits->inheritedWindowData = new osgViewer::GraphicsWindowWin32::WindowData( hwnd );
traits->setInheritedWindowPixelFormat = true;
traits->doubleBuffer = true;
traits->windowDecoration = true;
traits->sharedContext = NULL;
traits->supportsResize = true;

RECT rect;
::GetWindowRect( hwnd, &rect );
traits->x = 0;
traits->y = 0;
traits->width = rect.right - rect.left;
traits->height = rect.bottom - rect.top;

osg::ref_ptr<osg::GraphicsContext> gc = osg::GraphicsContext::createGraphicsContext( traits.get() );
viewer->getCamera()->setGraphicsContext( gc.get() );
viewer->getCamera()->setViewport( new osg::Viewport( 0, 0, traits->width, traits->height ) );
viewer->getCamera()->setProjectionMatrixAsPerspective(30.0f, static_cast<double>(traits->width)/static_cast<double>(traits->height), 1.0f, 10000.0f);
Problems
How come the mountain in the hang glider demo is completely white with no shading? OR my textured objects don't show textures
There are two likely causes:

The plugin to read the necessary image file format can't be found or wasn't compiled. For the hang glider demo this is the .rgb file format (osgdb_rgb). You need to compile the rgb plugin in this case.
The program can't find the data files it requires (textures). Make sure that you have downloaded the demo datafiles archive and extracted them. Make sure that the environment variables in the INSTALL file are set correctly, as these tell the viewer where to find the data. As of this writing they are OSGHOME, OSGDATA and OSG_FILE_PATH. To set the environment variables in Windows go to control panel->system->advanced->environment variables.
Why does OSG seem to ignore my near/far clipping planes?
When using osgViewer::Viewer (or osgUtil::SceneView), near and far clipping planes are recomputed on-the-fly based on the current eye point and viewable scene. This is by design to optimize the near/far range of the depth buffer, which might otherwise result in "z-fighting" artifacts if near and far are set to unreasonably small or large values.

You can override this behavior by calling:

viewe.getCamera()>setComputeNearFarMode(osgUtil::CullVisitor::DO_NOT_COMPUTE_NEAR_FAR)
For an insightful example of this feature check out the osgthirdpersonview example (which was added in version 2.4). It shows one window containing a normal scene and a second window showing the camera and clipping planes used in the first window. By manipulating the view in the first window you can see the changing clipping planes in the second one.

If I let OpenSceneGraph calculate my near and far clipping planes, how do I get the computed values?
This info is available through the cull visitor (class osgUtil::CullVisitor?).

When using an osgUtil::SceneView? it would be

sceneView->getCullVisitor()->getCalculatedNearPlane();
sceneView->getCullVisitor()->getCalculatedFarPlane();
When using osgViewer::Viewer you can get its osg::Camera (which is a subclass osg CullVisitor?) with

viewer->getCamera()
I am trying to run OpenSceneGraph example programs under Mac OS/X, but no window appears! What can I do?
You need to set the following environment variable before launching the program:

tcsh:
setenv DYLD_BIND_AT_LAUNCH 1
bash:
export DYLD_BIND_AT_LAUNCH=1
If you get dyld "can't open library" errors when running OSG programs under OSX, you may also need to set your DYLD_LIBRARY_PATH environment variable to point to the OSG libraries and/or plugins.

Hey, this particle system is cool, but looks strange when I position it in my scene. What's up?
You are probably rotating both the particle systems and the particle emitters. The tranform above the particle system(s) should match your world's (absolute) coordinate frame, or the reference frame that "contains" the particles (for example, an airplane or a car). To transform a particle system inside this reference frame you should transform only the emitters, not the ParticleSystem drawables. If you apply a transform above "fountain.osg" you actually apply a translation/rotation to both emitters and particle systems; to get a correct behavior you should traverse the scene graph and avoid applying the transform to any geodes containing ParticleSystem drawables. (answer courtesy Marco Jez)

There is a diagram, description and source code to do this here: http://faculty.nps.edu/jasullivan/osgTutorials/osgParticleHelper.htm

I'm having a problem using a PrimitiveSet to represent a single point OR my geometry seems to dissappear as it gets very far away. What's wrong?
By default the OSG uses small feature culling to cull out objects that occupy less than a predetermined screen size. This is a valuable feature for models with many details which do not contribute to the visual quality of the model when viewed from a distance. You can completely disable small feature culling by changing the cullingMode on the viewers osg::Camera with:

osg::CullStack::CullingMode cullingMode = viewer.getCamera()->getCullingMode();
cullingMode &= ~(osg::CullStack::SMALL_FEATURE_CULLING);
viewer.getCamera()->setCullingMode( cullingMode );
You can also control the size of the screen space that is used to cull small features with

viewer.getCamera()->setSmallFeatureCullingPixelSize( minimumSize );
When I apply a scaling factor in a osg::MatrixTransform, my models are displayed washed out or dark. What's up?
The model's normals are probably scaled along with its vertices. To keep normals normalized, set the OpenGL attribute GL_RESCALE_NORMALS on the appropriate stateset:

stateSet->setMode( GL_RESCALE_NORMAL, osg::StateAttribute::ON );
Can I use OSG within an existing renderer?
(Wiki editing note: Split off in separate page)

It takes a little work, but it is entirely possible to use OSG within a pre-existing rendering system.

First of all, the central object you should know about are osgViewer::Viewer coupled with osgViewer::GraphicsWindowEmbedded. These two classes will manage the OSG specific rendering tasks. The osgviewerSDL and osgviewerGLUT example illustrate use of the Viewer and GraphicsWindowEmbedded?.

The setup of these two objects will look something like this:

viewer.getCamera()->setComputeNearFarMode( osgUtil::CullVisitor::DO_NOT_COMPUTE_NEAR_FAR );
viewer.setSceneData( rootNode );
Note, just replace rootNode with your actual root node for you OSG models.

NOTE: The call to setComputeNearFarMode is very important. If you don't do this, then OSG will use a different near and far plane when rendering its objects, and they will have different values in the depth-buffer than the rest of your scene. This can lead to very odd effects.

If you want to use lighting that is different from what the rest of your renderer is using, you might want to call either:

viewer.setLightingMode( osg::View::SKY_LIGHT );
or

viewer.setLightingMode( osg::View::HEADLIGHT );
That's basically it for setup.

Now you just need to call !Viewer for rendering, and this requires a little extra work.

First off, it is recommended that you call glPushAttribs( GL_ALL_ATTRIB_BITS ) and glPushMatrix for each of the modelview, projection and texture matrices before calling your other OpenGL code, and the corresponding pop fuctions afterwards, and do the same with OSG. This prevents OSG and your other OpenGL code from interfering with each other. For example:

glPushAttrib=]( GL_ALL_ATTRIB_BITS );
glMatrixMode=](GL_PROJECTION);
glPushMatrix();
glMatrixMode(GL_TEXTURE);
glPushMatrix();
glMatrixMode(GL_MODELVIEW);
glPushMatrix();

your code here...


glMatrixMode(GL_TEXTURE);
glPopMatrix();
glMatrixMode(GL_PROJECTION);
glPopMatrix();
glMatrixMode(GL_MODELVIEW);
glPopMatrix();
glPopAttrib();
The next important thing for using !Viewer is that you need to tell it about your pre-existing viewport and projection and modelview matrices. The code to do that looks like this:

GLint viewParams[4];
glGetIntegerv( GL_VIEWPORT, viewParams );
viewer.getCamera()->setViewport(viewParams[0], viewParams[1], viewParams[2], viewParams[3]);

GLdouble glMat[16];

glGetDoublev( GL_PROJECTION_MATRIX, glMat );

viewer.setProjectionMatrix( osg::Matrix(glMat) );

glGetDoublev( GL_MODELVIEW_MATRIX, glMat );

viewer.setViewMatrix( osg::Matrix(glMat) );
Lastly, you need to make the actual calls to the !Viewer object:

viewer.frame();
If you do all of that, you should be able to successfully use OSG within your pre-existing rendering system, thereby gaining many of the advantages of OSG, without having to scrap your existing system.

I have derived a class from osg::Drawable, but its drawImplementation() method is called only once
Try disabling the use of display lists for this class.

drawable->setUseDisplayList( false );
Otherwise a display list will be created once and this will be called for drawing your drawable next time instead of your drawImplementation.

How can I get the BoundingBox for a loaded Node or 3D model?
To obtain an axis aligned osg::BoundingBox for a graph

 osg::ComputeBoundsVisitor  cbv;
 osg::BoundingBox           &bb(cbv.getBoundingBox());

 pNode->accept(cbv);
// access as bb._min.x(), etc
For performance reasons the OSG stores osg::BoundingSphere's for all internal nodes, and osg::BoundingBox's for the Drawable leaves.

If you wish to use a BoundingBox of a node then you can convert the BoundingSphere to a BoundingBox by doing something like:

 BoundingBox bb;
 bb.expandBy(node->getBound());
When using multiple viewers and/or multiple rendering windows, I get weird results and my textures don't display correctly
Note, for osgViewer based viewers the is native support for multiple rendering windows so no problems should occur, however, for viewers that are rolled my users themselves such as usiong the low level osgUtil::SceneView? issues can arise, the rest of the entry applies to this type of usage.

Each rendering window has its own OpenGL context which is separate from all other contexts. Since OSG doesn't know how you have set up your windowing environment, you need to ensure that each osg::State object is tied to a unique OpenGL context. To do that you should:

for each window, get the associated osgUtil::SceneView object
for each SceneView object, get the associated osg::State object
call State::setContextID() on each State, passing a unique number to identify that context.
After contracting the SceneView?'s:

// this will automatically create the osg::State amoung other operations
 sceneview0->setDefaults();
// now set the ID to 0 (this is the default, just set here for clarity
 sceneview0->getState()->setContextID(0);

 sceneview1->setDefaults();
 sceneview1->getState()->setContextID(1);
NOTE: context IDs are used as indices in vectors that grow automatically, so please avoid setting large numbers. Start counting from 0 and then increment by one each time.

I have two or more views sharing a scene graph, but I want to limit what part of the scene graph is shown in one or more of the views. How do I do that?
What is drawn in a view depends on the results of the Cull Traversal. Each view will have a unique osgViewer::View and a each osgViewer::Viewer will have a unique cull traversals mask. You can set a traversal mask on each View (or sceneView's cullSettings), which it will apply (as a bitwise AND) to each of the nodes it traverses. On each node, then, you can set a CullMask that corresponds to the view you want that sub-graph to be displayed in.

Like this:

  lefView->setCullMask( 0x1);
  rightView->setCullMask( 0x2 );


  leftNode->setNodeMask(0x1);
  rightNode->setNodeMask(0x2);

On previous question - Yeah but.... it didn't work!
(Wiki editing note: references osgProducer::Viewer )

When using osgProducer::Viewer, convenience functions are set up to allow attributes to be set globally for all Cameras and SceneHandler (including SceneViews) in an OsgCameraGroup. This includes traversal masks for CullVisitors, which will all be set to 0xFFFFFFFF by default. Before setting the TraversalMask on the unique [=CullVisitors?=], you need to make them immune to imposition of global settings with this (CullSettings are applied to CullVisitors on traversal):

    osgProducer::Viewer::SceneHandlerList shl = viewer.getSceneHandlerList();
    osgProducer::Viewer::SceneHandlerList::iterator p;
    unsigned int n = 0;
    for( p = shl.begin(); p != shl.end(); p++ )
    {
        int inheritanceMask = (*p)->getSceneView()->getInheritanceMask();
        inheritanceMask &= ~(osg::CullSettings::CULL_MASK);
        (*p)->getSceneView()->setInheritanceMask( inheritanceMask );
        (*p)->getSceneView()->setCullMask( 1<<(n));
        n++;
    }
How do I capture a screengrab?
(Wiki editing note: references Producer ) (Wiki editing note: there used to be functionality in osgviewer to do this, but it seems gone? )

For current OSG, take a look at the osgscreencapture example program. In essence, you simply need to attach a Camera post-draw callback. Here's a very simple example:

struct CaptureCB : public osg::Camera::DrawCallback
{
    CaptureCB( int w, int h )
      : w_( w ), h_( h )
    {}

    virtual void operator()( osg::RenderInfo& ri ) const
    {
        std::string fName( "screen.png" ) );
        osg::ref_ptr<osg::Image> image = new osg::Image;
        image->readPixels( 0, 0, w_, h_, GL_RGBA, GL_UNSIGNED_BYTE );
        osgDB::writeImageFile( *image, fName );
    }

    int w_, h_;
};
Producer example from ViewerEventHandler.cpp ViewerEventHandler::SnapImageDrawCallback:

int x,y;
unsigned int width,height;
camera.getProjectionRectangle(x,y,width,height);
osg::ref_ptr<osg::Image> image = new osg::Image;
image->readPixels(x,y,width,height, GL_RGB,GL_UNSIGNED_BYTE);
osgDB::writeImageFile(*image,_filename);
GLUT example from the SST Project:

osg::ref_ptr<osg::Image>image = new osg::Image;
unsigned int w = glutGet(GLUT_WINDOW_WIDTH);
unsigned int h = glutGet(GLUT_WINDOW_HEIGHT);
image->allocateImage(w, h, 1, GL_RGB, GL_UNSIGNED_BYTE);
image->readPixels(0, 0, w, h, GL_RGB, GL_UNSIGNED_BYTE);
Why does my framerate drop when rendering point sprites to an FBO/pbuffer?
Short answer: Change the coordinate origin mode of the PointSprite attribute to LOWER_LEFT:

osg::PointSprite *ps = new osg::PointSprite;
ps->setCoordOriginMode(osg::PointSprite::LOWER_LEFT);
Long answer: Read the section on Point Sprites in the nVidia OpenGL 2.0 Support document. It states the following:

When rendering to pixel buffers (commonly called pbuffers) or frame buffer objects (commonly called FBOs), change the GL_POINT_SPRITE_COORD_ORIGIN state set to GL_LOWER_LEFT setting for fully hardware accelerated rendering. Using GL_UPPER_LEFT with pbuffer and FBO rendering will force points to be transformed on the CPU.

Why does my geometry renders opaque while I have transparent colors and/or materials attached to it ?
You need to activate OpenGL blending by setting the GL_BLEND mode on the geometry's stateset (or that of a parent node).

stateSet->setMode( GL_BLEND, osg::StateAttribute::ON );
Or in a .osg file:

file geom.osg

  Geometry {
    [...]
    StateSet {
      GL_BLEND ON
    }
    PrimitiveSets 1
    {
    [..]
I wrote a scene containing a particle system to a .ive file, but some nodes/drawables seem to be missing
(Wiki editing note: Is this still valid with 2.4?)

Some nodes and drawables in the osgParticle nodekit are currently not supported in .ive files. As a workaround you can save to a .osg file instead.

Older versions of OpenSceneGraph
During compile I get errors about Producer/*: No such file or directory. Why? - happens with daily builds and 0.9.4-2 official.
First build and install OpenProducer.

Can I use OSG without Producer, and/or with already created MFC or WxWindow windows ?
You can use OSG with or without Producer, even if you are creating your own windows. See the osgsimple example for an example of using OSG with a generic windowing environment. OSG itself is windowing system agnostic, so setting up the window and OpenGL graphics context will be up to your application. osgsimple uses Producer, but is written in a way to provide you the skeleton to use your own windowing system.

Alternatively, you can use Producer in your own windowing environment as well by setting each Camera's RenderSurface to the window you've created. Like this:

osgProducer::Viewer viewer;
viewer.getCamera(0)->getRenderSurface()->setWindow( myWindow );
The variable 'myWindow' is an X11 Window, or a win32 HWND.

See : http://osgcvs.no-ip.org/osgarchiver/archives/November2004/1019.html for even more details.

How can I change the Producer icon at run-time?
In Microsoft Windows and Visual Studio 7.x:

First add an icon to your solution (Project/Add Recource/Icon).

After viewer->realize() do the following:

Producer::Window wnd = viewer->getCamera(0)->getRenderSurface()->getWindow();
HICON h1 = LoadIcon(GetModuleHandle(0), "YOUR_ICON");
DWORD dw = SetClassLongPtr(wnd, GCL_HICON, (LONG_PTR)h1);
The string "YOUR_ICON" should refer to the icon name in your resource file(.rc).

Math, Matrices, Vectors, Quaternions
(Wiki editing note: also describe Z-up convention)

What multiplication order do the matrix, vector and quaternion classes in OSG use?
The OSG uses post-multiplication order. For example, if you want to create a matrix that first scales by 50% on all axes, then rotates 90 degrees around the X axis and finally translates 2 units in the X direction you would use

osg::Matrix M = osg::Matrix::scale(0.5, 0.5, 0.5) 
                * osg::Matrix::rotate(osg::inDegrees(90), osg::X_AXIS) 
                * osg::Matrix::translate(2, 0, 0));

// Use matrix M with, for example, an osg::MatrixTransform to transform its child nodes
osg::ref_ptr<osg::MatrixTransform> mt = new osg::MatrixTransform(M);
To transform a vertex v with matrix M you can use v * M.

Note that angles are passed in radians. You can convert from degrees to radians by using one of

osg::inDegrees(angle_in_degrees);
osg::DegreesToRadians(angle_in_degrees);
Conversion from radians to degrees can be done with osg::inRadians() or osg::RadiansToDegrees().

I have another question not answered here…
Check the Matrix and Quaternion FAQ at http://www.j3d.org/matrix_faq/
