// 想直接變成能用的網站，可以把這個 React 頁面放進免費的 Vercel + Supabase。
// 1. 到 Supabase 建立專案
// 2. 建立 photocard_posts 資料表：id、idol、title、price、image_url
// 3. 在 .env.local 放入：
// NEXT_PUBLIC_SUPABASE_URL=你的網址
// NEXT_PUBLIC_SUPABASE_ANON_KEY=你的金鑰
// 4. 用 Vercel 匯入 GitHub 專案即可直接上線

export default function PhotocardMarketplace() {
  const cards = [
    {
      id: 1,
      idol: "劉宇寧",
      title: "影視收藏卡｜稀有閃卡",
      price: "$380",
      image: "https://images.unsplash.com/photo-1511367461989-f85a21fda167?w=800"
    },
    {
      id: 2,
      idol: "成毅",
      title: "簽售特典小卡",
      price: "$250",
      image: "https://images.unsplash.com/photo-1524504388940-b1c1722653e1?w=800"
    },
    {
      id: 3,
      idol: "檀健次",
      title: "演唱會限定小卡",
      price: "$420",
      image: "https://images.unsplash.com/photo-1494790108377-be9c29b29330?w=800"
    }
  ];

  return (
    <div className="min-h-screen bg-pink-50 text-gray-800">
      <header className="bg-white shadow-sm border-b border-pink-100 sticky top-0 z-10">
        <div className="max-w-6xl mx-auto px-4 py-4 flex items-center justify-between">
          <div>
            <h1 className="text-2xl font-bold text-pink-500">Card Closet</h1>
            <p className="text-sm text-gray-500">你的內娛小卡櫃</p>
          </div>

          <nav className="hidden md:flex gap-6 text-sm font-medium">
            <button>首頁</button>
            <button>全部小卡</button>
            <button>我的小卡櫃</button>
            <button>私訊</button>
            <button>登入 / 註冊</button>
          </nav>
        </div>
      </header>

      <section className="max-w-6xl mx-auto px-4 py-10">
        <div className="bg-gradient-to-r from-pink-300 to-rose-200 rounded-3xl p-8 shadow-lg mb-10">
          <h2 className="text-4xl font-bold mb-3">賣掉你不收的小卡 ✨</h2>
          <p className="text-lg text-gray-700 mb-6">
            上架、交換、私訊，一個專門給追星女生的小卡網站。
          </p>

          <div className="flex flex-wrap gap-3">
            <button className="bg-white text-pink-500 px-5 py-3 rounded-2xl font-semibold shadow">
              我要賣小卡
            </button>
            <button className="bg-pink-500 text-white px-5 py-3 rounded-2xl font-semibold shadow">
              逛逛全部小卡
            </button>
          </div>
        </div>

        <div className="flex flex-col md:flex-row gap-4 mb-8">
          <input
            className="flex-1 rounded-2xl border border-pink-200 px-4 py-3"
            placeholder="搜尋偶像、團體、卡種..."
          />
          <select className="rounded-2xl border border-pink-200 px-4 py-3 bg-white">
            <option>全部分類</option>
            <option>專輯小卡</option>
            <option>簽售特典</option>
            <option>演唱會限定</option>
          </select>
        </div>

        <div className="grid md:grid-cols-3 gap-6">
          {cards.map((card) => (
            <div
              key={card.id}
              className="bg-white rounded-3xl overflow-hidden shadow-md hover:shadow-xl transition"
            >
              <img
                src={card.image}
                alt={card.title}
                className="h-64 w-full object-cover"
              />

              <div className="p-5">
                <p className="text-sm text-pink-400 font-medium mb-1">{card.idol}</p>
                <h3 className="font-bold text-lg mb-2">{card.title}</h3>
                <div className="flex items-center justify-between">
                  <span className="text-2xl font-bold text-pink-500">{card.price}</span>
                  <button className="bg-pink-500 text-white px-4 py-2 rounded-xl">
                    私訊賣家
                  </button>
                </div>
              </div>
            </div>
          ))}
        </div>

        <section className="mt-14 grid md:grid-cols-3 gap-5">
          <div className="bg-white rounded-3xl p-5 shadow">
            <h3 className="font-bold text-lg mb-2">登入 / 註冊</h3>
            <p className="text-sm text-gray-600">
              使用 Email 建立帳號，之後就能收藏、賣卡、聊天。
            </p>
          </div>

          <div className="bg-white rounded-3xl p-5 shadow">
            <h3 className="font-bold text-lg mb-2">我的小卡櫃</h3>
            <p className="text-sm text-gray-600">
              可以把自己有的卡整理成櫃子，也能標示「可售」或「想收」。
            </p>
          </div>

          <div className="bg-white rounded-3xl p-5 shadow">
            <h3 className="font-bold text-lg mb-2">私訊功能</h3>
            <p className="text-sm text-gray-600">
              買家和賣家可以直接聊天、討論價格和交換。
            </p>
          </div>
        </section>
      </section>
    </div>
  );
}
