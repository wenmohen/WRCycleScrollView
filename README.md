# WRCycleScrollView
WRCycleScrollView
源代码路径:https://github.com/wangrui460/WRCycleScrollView

How To Use


var cycleScrollView:WRCycleScrollView?
let height = 520 * kScreenWidth / 1080.0
let frame = CGRect(x: 0, y: 150, width: kScreenWidth, height: height)
// 可加载网络图片或者本地图片
let serverImages = ["http://p.lrlz.com/data/upload/mobile/special/s252/s252_05471521705899113.png",              "http://p.lrlz.com/data/upload/mobile/special/s303/s303_05442007678060723.png",                  "http://p.lrlz.com/data/upload/mobile/special/s303/s303_05442007587372591.png",                    "http://p.lrlz.com/data/upload/mobile/special/s303/s303_05442007388249407.png",                    "http://p.lrlz.com/data/upload/mobile/special/s303/s303_05442007470310935.png"]
// 构造方法
cycleScrollView = WRCycleScrollView(frame: frame, type: .SERVER, imgs: serverImages)
view.addSubview(cycleScrollView!)
// 添加代理
cycleScrollView?.delegate = self
代理方法


extension ServerImgController: WRCycleScrollViewDelegate
{
/// 点击图片事件
func cycleScrollViewDidSelect(at index:Int, cycleScrollView:WRCycleScrollView)
{
print("点击了第\(index+1)个图片")
}

/// 图片滚动事件
func cycleScrollViewDidScroll(to index:Int, cycleScrollView:WRCycleScrollView)
{
print("滚动到了第\(index+1)个图片")
}
}
