# Native Asset Bundle Sample 

***Disclaimer:*** This project is based on a project that was officially distributed by Unity Technologiies for version 4.x and 5.x which is no longer distributed/supported.

I decided to upgrade this project to Unity 2020.3 LTS for learning and testing purposes. I tested it on Win 11 with no issues, and I plan to test it next on Android.

My favorite way to test it:
1. Open Unity project
2. Click on *Support -> AssetBundles -> Build AssetBundles*
3. Click on *Support -> AssetBundles -> Local Asset Bundle Server*
4. Run any scene from *Assets/AssetBundleSample/Scenes/*.unity*

Below, the original documentation that Unity Technologies used to share with the original project.

## Explanation
-----------

The intent of the asset bundle manager is to provide a high-level API and a set
of editor utilities to build, test and use asset bundles in a refined workflow,
rather than using Unity's low-level AssetBundle API directly.

In this demo, we demonstrate:

- Automatic asset bundle dependency resolving & loading.
  Dependencies between asset bundles are tracked in a single "Manifest" asset
  bundle. This manifest holds information about all asset bundles and their
  dependencies built for a particular target platform. In this way it's possible
  to automatically resolve dependent asset bundles before the asset bundle itself
  is downloaded.

- Automatic unloading of asset bundles. When an asset bundle or a dependency
  thereof is no longer needed, the asset bundle is unloaded.

- Editor simulation. Allows to test the project in editor mode without actually
  building the assetBundles.

- Optional setup in which all asset bundles are downloaded.

- Build pipeline postprocessor and integration so that building a player builds
  the asset bundles and puts them into the player data (Default implementation for
  loading assetbundles from disk on any platform).

- AssetBundle variants. A prioritized list of variants that should be used if the
  asset bundle with that variant exists, first variant in the list is the most
  preferred etc.

## Editor utilities and High-level API
-----------------------------------

The editor utilities are accessible via Assets>AssetBundles menu. The following
utilities are provided:

Simulation Mode
    This is used to control asset bundle simulation in the Editor.
    When simulation mode is enabled, the editor is in play mode and asset
    bundles are simulated based on the current build target. Asset bundles
    can be "used" as if built and deployed without actually building them.
    Asset bundle variants are not simulated in simulation mode.

Build AssetBundles
    Builds the currently assigned asset bundles for the current target platform.
    The built asset bundles are placed into "AssetBundles" folder on the root
    of the project. This folder is configurable. Separate subfolders within
    AssetBundles folder are used for each target platform.

Local AssetBundle Server
    A local server is created allowing access to the built asset bundles. The
    asset bundles can be accessed by any test application that has access to
    the same local network as the computer that the editor runs on. This allows
    to test the AssetBundle workflow  of a project without having to actually
    deploy built asset bundles.

For more information on the high-level API provided by the asset bundle manager,
see explanation in the AssetBundleManager.cs file.

## Scenes
------

There're 4 scenes under Assets/TestScenes folder:

### AssetLoader.unity

    Demonstrates how to load a normal asset from asset bundle.
    Additional information can be found in LoadAssets.cs script.

###  SceneLoader.unity

    Demonstrates how to load a scene from asset bundle.
    Additional information can be found in LoadScenes.cs script.

###  VariantLoader.unity

    Demonstrates how to load variant asset bundle.
    Additional information can be found in LoadVariants.cs script.

    Asset bundle variants allow to load different version of the same asset
    depending on user-defined settings. For example, it's possible to
    configure low-end devices to use low resolution texture and high-end
    devices to use high resolution texture.

    In the demo, the following resources are built:

        1. "My Assets HD" folder into "variant/myassets.hd" asset bundle.
            This is "hd" variant of "myassets" asset bundle.
        2. "My Assets SD" folder into "variant/myassets.sd" asset bundle.
            This is "sd" variant of "myassets" asset bundle.
        3. "variant-scene.unity" into "variants/variant-scene.unity3d".
            This asset bundle contains a scene which uses variant asset bundle:
            either from "myassets.hd" or "myassets.sd".

    Assets within variant asset bundles must match across entire family of
    variants. That is, if one variant provides an asset, all variants must
    provide some asset with the same name.

    Variant asset bundles always have an extension, which matches with
    variant name. E.g. "myassets.hd" asset bundle is "hd" variant of
    "myassets" asset bundle.

    The active variant may be changed in LoadVariants.cs.

    Please also refer to AssetBundleManager.RemapVariantName() to see how to
    resolve the correct AssetBundle according to the active variant.

    Asset bundle variants may not be simulated in editor.

###  TanksLoader.unity

    Demonstrates how to load different variant asset bundles dynamically.

## License
-------

The project is released by Unity Technologies under the MIT/X11 license; see the
LICENSE file.

This means that you pretty much can customize and embed it in any software under
any license without any other constraints than preserving the copyright and
license information while adding your own copyright and license information.

You can keep the source to yourself or share your customized version under a
compatible license.
