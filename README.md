# UE4 crashing bug while using MaterialBillboard and RectLight components together

## Steps to reproduce
1) Load the project on the TestMap
2) Play the level with the standalone game option

## Example stacktrace

    Assertion failed: IsInGameThread() || IsAsyncLoading() [File:D:/Build/++UE4+Licensee/Sync/Engine/Source/Runtime/Engine/Private/Materials/MaterialInstance.cpp] [Line: 622]

    UE4Editor_Core!AssertFailedImplV() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Core\Private\Misc\AssertionMacros.cpp:100]
    UE4Editor_Core!FDebug::CheckVerifyFailedImpl() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Core\Private\Misc\AssertionMacros.cpp:450]
    UE4Editor_Engine!UMaterialInstance::GetMaterial() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Engine\Private\Materials\MaterialInstance.cpp:622]
    UE4Editor_Engine!UMaterialInterface::GetRelevance() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Engine\Private\Materials\MaterialInterface.cpp:236]
    UE4Editor_Engine!FMaterialSpriteSceneProxy::FMaterialSpriteSceneProxy() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Engine\Private\Components\MaterialBillboardComponent.cpp:86]
    UE4Editor_Engine!UMaterialBillboardComponent::CreateSceneProxy() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Engine\Private\Components\MaterialBillboardComponent.cpp:296]
    UE4Editor_Renderer!FScene::AddPrimitive() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Renderer\Private\RendererScene.cpp:1291]
    UE4Editor_Engine!<lambda_1c454102935558661824d22f5ad28ce6>::operator()() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Engine\Private\Components\ActorComponent.cpp:92]
    UE4Editor_Engine!ParallelForImpl::TParallelForData<TFunctionRef<void __cdecl(int)> >::Process() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Core\Public\Async\ParallelFor.h:169]
    UE4Editor_Engine!TGraphTask<ParallelForImpl::TParallelForTask<TFunctionRef<void __cdecl(int)> > >::ExecuteTask() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Core\Public\Async\TaskGraphInterfaces.h:849]
    UE4Editor_Core!FTaskThreadAnyThread::ProcessTasks() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Core\Private\Async\TaskGraph.cpp:1039]
    UE4Editor_Core!FTaskThreadAnyThread::ProcessTasksUntilQuit() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Core\Private\Async\TaskGraph.cpp:863]
    UE4Editor_Core!FTaskThreadAnyThread::Run() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Core\Private\Async\TaskGraph.cpp:940]
    UE4Editor_Core!FRunnableThreadWin::Run() [D:\Build\++UE4+Licensee\Sync\Engine\Source\Runtime\Core\Private\Windows\WindowsRunnableThread.cpp:86]