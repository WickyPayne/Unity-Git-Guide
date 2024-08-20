# Best practices using Git with Unity

Main problem collaborating on project in Unity are **conflicts in Scene**, Prefab, etc. which are not easily mergeable. Using **Smart merge by Unity** can help reduce a headache of collaborating on project with your friend. Nevertheless conflict can happen, so try to **avoid changes in same scene**, it's similar as to artists are not working on same image file at the same time.

------


Warning: This guide is for **experienced users** with Unity and Git.

**Beginners with Git** start with:  
Getting started with Git using SourceTree (by Virtual Play): https://www.youtube.com/watch?v=UD7PV8auGLg&list=PLpL2ONl1hMLtlY1Y7YJNcA5zumvaITLYs

**Inexperienced with Git with Unity and scene conflicts** start with:  
Git & Unity (by Jason Weimann): https://www.youtube.com/watch?v=tNhIh3NzANc&list=PLB5_EOMkLx_X7VgZxsjsd2WatkjocMXcb

------

## Recommended Setup

**.gitignore**: https://github.com/github/gitignore

**.gitattributes**: https://gist.github.com/nemotoo/b8a1c3a0f1225bb9231979f389fd4f3f  

**IMPORTANT:** In Project Settings set Asset Serialization mode to Force text. (Edit -> Project Settings -> Editor -> **Asset Serialization** -> Mode: **Force text**)

**Smart merge** (UnityYamlMerge.exe):  
tool by Unity to merge Scene and Prefab files in a semantically correct way.  

It is set in .gitattributes to use Smart merge  
Don't forget to set your PATH environment variable to something like C:\Program Files\Unity\Hub\Editor\2020.3.25f1\Editor\Data\Tools\  

In case it's not working, you can explicitly set it in Sourcetree.  
Set Sourcetree to use UnityYamlMerge.exe as external diff/merge tool:  
*Example:*  
*Diff/Merge tool:* C:\Program Files\Unity\Hub\Editor\2020.3.25f1\Editor\Data\Tools\UnityYAMLMerge.exe  
*Arguments:* merge -p $BASE $REMOTE $LOCAL $MERGED

![Sourcetree Unity setup](https://raw.githubusercontent.com/WickyPayne/Unity-Git-Guide/main/SourcetreeSetup.png)

## Optional Setup

**Meld + Smart merge** *(optional)*: https://www.youtube.com/watch?v=EQB-N-ClO9g

**Scene Fusion** *(optional)*: plugin for Unity - real-time scene merger https://www.kinematicsoup.com/scene-fusion/pricing  

**Github For Unity** extension asset - deprecated not working anymore on this link https://unity.github.com/   
There is new Github for Unity (don't use one in asset store I guess) Just give it a try, I didn't try the new one yet.   
https://github.com/spoiledcat/git-for-unity  


------

## Collaboration - Best Practices

UnityYamlMerge.exe will help a lot BUT, best is to **avoid conflicts in scene** file.

**UnityYamlMerge**  
- ensure it's correctly setup and it's working. (see above)
- set .gitattributes to use Smart merge
- set your PATH env var for git to find it  

**Scene**:

- Work in different SCENES. One person putting all the SCENES together. Use Additive Scenes at the same time.
- After resolving merge conflict (before commiting it) test BOTH changes (if both wanted).
- Scene (and other changes) in separate commits.
- (optional: Use plugin Scene Fusion.)

Avoid changes in **Scene**:
- Use prefabs (different prefabs for different parts of UI)
- Split world to more areas(prefabs) (if you don't move prefab in a scene it will not modify scene)
- Use scriptable objects to store data
- cinematic/cutscene - nest Timelines (like prefabs)
- Use GithubForUnity extension - Lock scenes using git LFS lock.

Use Git LFS
- textures, models, audio, video, ...  
- not-recommended?: scenes, some assets, ... see conversation in .gitattributess gist (this is beyond me)

------

Sources:

**Introduction to Version Control | Unite Now 2020** (by Unity): https://www.youtube.com/watch?v=ISW2nS_v3Ic

**Git & Unity** (by Jason Weimann): https://www.youtube.com/watch?v=tNhIh3NzANc&list=PLB5_EOMkLx_X7VgZxsjsd2WatkjocMXcb

**Git with Unity for Game Development** (by Microsoft Developer):  
video: https://www.youtube.com/watch?v=GmRPCl4MzCA  
mentioned in video: https://aka.ms/gitwithunity - (redirects to https://edwardthomson.com/blog/git_with_unity.html )

**Smart merge manual**: https://docs.unity3d.com/Manual/SmartMerge.html  
