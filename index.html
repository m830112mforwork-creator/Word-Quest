import React, { useState, useEffect, useCallback, useRef } from 'react';
import { 
  Upload, Volume2, RefreshCcw, Image as ImageIcon, Lightbulb, Star, Trophy, 
  Heart, Clock, XCircle, CheckCircle, HelpCircle, Rocket, Type, 
  MousePointerClick, BookOpen, ArrowRight, ArrowLeft, Home, Shuffle, 
  Edit3, ImagePlus, Ear, CheckSquare, VolumeX 
} from 'lucide-react';

/**
 * ==========================================
 * 圖片處理元件 (Triple-Fallback Safe Image)
 * ==========================================
 */
const SafeImage = ({ src, word }) => {
  const [imgStatus, setImgStatus] = useState('loading');
  const [imgSrc, setImgSrc] = useState(src);

  useEffect(() => {
    setImgStatus('loading');
    setImgSrc(src);
  }, [src]);

  return (
    <div className="absolute inset-0 w-full h-full flex items-center justify-center bg-white rounded-sm overflow-hidden z-10">
      <div className="absolute inset-0 flex flex-col items-center justify-center bg-gradient-to-br from-orange-50 to-orange-100 text-orange-400 z-0">
        <HelpCircle size={72} className="mb-3 opacity-40" />
      </div>
      {imgStatus === 'loading' && (
        <div className="absolute inset-0 flex items-center justify-center bg-white/80 z-20">
          <div className="w-10 h-10 border-4 border-orange-300 border-t-orange-500 rounded-full animate-spin"></div>
        </div>
      )}
      {imgSrc && (
        <img
          src={imgSrc}
          alt={word}
          className={`w-full h-full object-contain relative z-10 ${imgStatus === 'loading' ? 'opacity-0' : 'opacity-100'}`}
          onLoad={() => setImgStatus('success')}
          onError={() => {
            const fallback = `https://api.dicebear.com/9.x/bottts/svg?seed=${encodeURIComponent(word)}`;
            if (imgSrc !== fallback) setImgSrc(fallback);
          }}
        />
      )}
    </div>
  );
};

const App = () => {
  // --- 狀態定義 ---
  const [appState, setAppState] = useState('upload'); 
  const [wordList, setWordList] = useState([]);
  const [currentIndex, setCurrentIndex] = useState(0);
  const [score, setScore] = useState(0);
  const [lives, setLives] = useState(3);
  const [isMuted, setIsMuted] = useState(false);

  // --- 檔案處理 ---
  const handleFileUpload = async (e) => {
    const file = e.target.files[0];
    if (!file) return;

    // 動態載入 XLSX 庫確保 GitHub Pages 運行流暢
    const script = document.createElement('script');
    script.src = "https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js";
    script.onload = () => {
      const reader = new FileReader();
      reader.onload = (evt) => {
        const wb = window.XLSX.read(evt.target.result, { type: 'array' });
        const data = window.XLSX.utils.sheet_to_json(wb.Sheets[wb.SheetNames[0]], { header: 1 });
        const parsed = data.slice(1).map(row => ({
          word: String(row[0] || '').trim().toLowerCase(),
          translation: row[1] || '',
          hasFetched: false
        })).filter(i => i.word);
        setWordList(parsed);
        setAppState('selectMode');
      };
      reader.readAsArrayBuffer(file);
    };
    document.head.appendChild(script);
  };

  return (
    <div className="min-h-screen bg-amber-50 font-sans">
      {/* Header */}
      <header className="bg-orange-600 p-4 text-white shadow-lg flex justify-between items-center">
        <h1 className="text-xl font-black flex items-center gap-2">
          <ImageIcon /> Spelling Adventure
        </h1>
        {wordList.length > 0 && (
          <button onClick={() => setAppState('upload')} className="bg-orange-700 px-3 py-1 rounded-lg text-sm">重新上傳</button>
        )}
      </header>

      <main className="max-w-4xl mx-auto p-6 flex flex-col items-center justify-center min-h-[80vh]">
        {appState === 'upload' && (
          <div className="bg-white p-10 rounded-3xl shadow-2xl border-4 border-orange-200 text-center scale-110">
            <Rocket size={60} className="mx-auto text-orange-500 mb-4" />
            <h2 className="text-2xl font-bold mb-6">準備好開始單字大冒險嗎？</h2>
            <label className="cursor-pointer bg-orange-500 hover:bg-orange-600 text-white px-8 py-4 rounded-full font-black text-lg transition-all inline-block shadow-lg">
              上傳 Excel 題庫
              <input type="file" className="hidden" onChange={handleFileUpload} accept=".xlsx" />
            </label>
            <p className="mt-4 text-slate-400 text-sm">支援 .xlsx 格式 (A欄單字, B欄翻譯)</p>
          </div>
        )}

        {appState === 'selectMode' && (
          <div className="grid grid-cols-1 sm:grid-cols-2 gap-6 w-full">
            <button onClick={() => setAppState('playing')} className="bg-white p-8 rounded-3xl shadow-xl hover:-translate-y-2 transition-all border-b-8 border-blue-500">
              <Type size={48} className="text-blue-500 mb-4 mx-auto" />
              <div className="text-xl font-black">開始拼字挑戰</div>
            </button>
            <button onClick={() => setAppState('edit')} className="bg-white p-8 rounded-3xl shadow-xl hover:-translate-y-2 transition-all border-b-8 border-purple-500">
              <Edit3 size={48} className="text-purple-500 mb-4 mx-auto" />
              <div className="text-xl font-black">自定義圖片</div>
            </button>
          </div>
        )}

        {/* 遊戲中與其它狀態... (邏輯同前) */}
        {appState === 'playing' && wordList.length > 0 && (
          <div className="text-center">
            <div className="relative w-64 h-64 mx-auto mb-8 shadow-2xl rounded-2xl overflow-hidden border-8 border-white">
              <SafeImage src={wordList[currentIndex].image} word={wordList[currentIndex].word} />
            </div>
            <h2 className="text-4xl font-black text-slate-800 tracking-widest">{wordList[currentIndex].word}</h2>
            {/* 拼字邏輯與 UI 按鈕 */}
          </div>
        )}
      </main>
    </div>
  );
};

export default App;
