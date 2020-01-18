### 资源管理器 (ResourceManager)

创建资源管理器
```C#
public void Start()
{
	// 如果你不打算写自定义的补丁更新流程，那么AssetBundle服务接口可以直接使用补丁管理器
	IBundleServices bundleServices = MotionEngine.GetMoudle<PatchManager>();

	// 设置参数
	var createParam = new ResourceManager.CreateParameters();
	createParam.AssetRootPath = "Assets/Works/Resource";
	createParam.SimulationOnEditor = true;
	createParam.BundleServices = bundleServices;
	createParam.DecryptServices = null;
	createParam.AutoReleaseInterval = 10;

	// 创建模块
	MotionEngine.CreateModule<ResourceManager>(createParam);
}
```

资源的加载教程请参考[资源系统](https://github.com/gmhevinci/MotionFramework/blob/master/Docs/Engine.Resource.md)

更详细的教程请参考示例代码
1. [Module.Resource/ResourceManager.cs](https://github.com/gmhevinci/MotionFramework/blob/master/Assets/MotionFramework/Scripts/Runtime/Module/Module.Resource/ResourceManager.cs)