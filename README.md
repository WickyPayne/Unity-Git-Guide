# Best practices using Git with Unity

------


Warning: This guide is for **experienced users** with Unity and Git.

------

**Beginners** start with:

Getting started with Git using SourceTree (by Virtual Play): https://www.youtube.com/watch?v=UD7PV8auGLg&list=PLpL2ONl1hMLtlY1Y7YJNcA5zumvaITLYs

Git & Unity (by Jason Weimann): https://www.youtube.com/watch?v=tNhIh3NzANc&list=PLB5_EOMkLx_X7VgZxsjsd2WatkjocMXcb

------

## Recommended Setup

**.gitignore**: https://github.com/github/gitignore
**.gitattribute**: https://gist.github.com/nemotoo/b8a1c3a0f1225bb9231979f389fd4f3f 

**Smart merge** (UnityYamlMerge.exe): tool by Unity to merge scene and Prefab files in a semantically correct way.

Set Sourcetree to use UnityYamlMerge.exe as external diff/merge tool:

example:

*Diff/Merge tool:* C:\Program Files\Unity\Hub\Editor\2020.3.25f1\Editor\Data\Tools\UnityYAMLMerge.exe 
*Arguments:* merge -p $BASE $REMOTE $LOCAL $MERGED

![SourcetreeUnity](D:\git\gist\UnityGitSetup\SourcetreeUnity.png)

(source1: https://docs.unity3d.com/Manual/SmartMerge.html )
(source2: Unity3D - How to Merge Scenes in GIT (by Jason Weimann) [time 3:40] https://youtu.be/yQvbaBgxA34?t=220)

## Optional Setup

**Meld + Smart merge** *(optional)*: https://www.youtube.com/watch?v=EQB-N-ClO9g

**Scene Fusion** (optional): plugin for Unity - real-time scene merger https://www.kinematicsoup.com/scene-fusion/pricing