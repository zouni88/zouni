#workmanager 轻量级后台任务管理

## worker  任务体
```kotlin
class DatabaseWork(context: Context, workerParams: WorkerParameters) : Worker(context,workerParams) {
    companion object{

    }

    override fun doWork(): Result {
        Log.e("cgq","start")
        val data = Data.Builder().putString("cgq","woker-data").build()
        setProgressAsync(data)
        return Result.success()
    }

}

```

## workerRequest  执行任务
## WorkerManager enqueue 添加任务 
```kotlin
    val workRequest: WorkRequest = OneTimeWorkRequestBuilder<DatabaseWork>().build()
    //状态回调，添加一个任务观察者
    WorkManager.getInstance(requireActivity()).getWorkInfoByIdLiveData(workRequest.id).observe(requireActivity()){
        when (it.state) {
            WorkInfo.State.RUNNING -> Log.e("cgq", "running======")
            WorkInfo.State.CANCELLED -> Log.e("cgq", "cancelled======")
            WorkInfo.State.SUCCEEDED ->Log.e("cgq", "success======")
            else -> Log.e("cgq", "都不对")
        }
    }
    WorkManager.getInstance(requireContext()).enqueue(workRequest)
```


