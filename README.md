# Kubernetes TLS Community

Welcome to the Kubernetes TLS community!

- [Introduction](#introduction)
- [Community meeting](#community-meeting)
- [Questions and issues](#questions-and-issues)

## Introduction

KLTS, known as Kubernetes Long Term Support, has a primary mission to provide free long-term maintenance support for earlier versions of Kubernetes.

Kubernetes versions are expressed as x.y.z, where x is the major version, y is the minor version, and z is the patch version. For the versions maintained by KLTS, it is followed by a string beginning with lts.

Visit [klts.io](https://klts.io/) for in-depth information about using KLTS.

## Community meeting

Regular KTLS Meeting: Tuesday at 23:00 PT (Pacific Time) (biweekly). [Convert to your timezone](http://www.thetimezoneconverter.com/?t=11:00&tz=PT%20%28Pacific%20Time%29).
  * [Meeting notes and Agenda]().
  * [Meeting recordings]().


## Contact

* sclak: [# klts](https://klts.slack.com/archives/C02H8DMB6SZ)

* [Open Community Issues/PRs](https://github.com/klts-io/kubernetes-lts/issues)

* Steering Committee Liaison: wzshiming(**[@wzshiming](https://github.com/wzshiming)**)

<!--

## 怎么加添补丁

1. 修改 release.yaml 文件， 加入补丁信息，然后在小于此版本的版本都要添加补丁名称
2. 运行 make verify-patch 校验所有补丁是否冲突
3. 如果有冲突，将 path 文件添加到 patches 目录下
4. 重新在 release.yaml 中修改补丁名称
5. 执行下面命令，当执行到解决冲突的阶段
QUIET=n ./hack/format_patch.sh patches/{{patchname}}.patch
6. 另外打开一个终端，解决冲突文件后添加到仓库，保证 git status 干净
7. 回到终端，输入 y 确认

-->

## How to add a patch to Kubernetes TLS

step:<br>
1. Modify the [release.yaml](https://github.com/klts-io/kubernetes-lts/blob/main/releases.yml) config to add the patch information, and then add the patch name for any version less than that

2. run `make verify-patch` command to check whether all patches conflict. e.g.:

```shell
make v1.14.10-lts.0
``` 

3. If there is a conflict, add the PATH file to the [Patches](https://github.com/klts-io/kubernetes-lts/tree/main/patches) directory as prompted

4. Change the patch name again in [release.yaml](https://github.com/klts-io/kubernetes-lts/blob/main/releases.yml)

5. Execute the following command when the execution reaches the conflict resolution stage：

```shell
QUIET=n ./hack/format_patch.sh patches/{{patchname}}.patch
```

6. Open another terminal, resolve the conflicting files and add them to the repository to ensure `git status` is clean

7. Go back to the terminal and type y to confirm

## Questions and issues

If you have questions or issues with KLTS, You can create issues in the [list](https://github.com/klts-io/kubernetes-lts/issues). Of course, you are familiar with KLTS, you can pick from list to solve. We will be very grateful for this.





