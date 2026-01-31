import React, { useState, useEffect } from 'react';
import { Home, CheckCircle, XCircle, Trophy, Star, ArrowRight, RefreshCw, Info, BookOpen, Lightbulb } from 'lucide-react';

const exercises = [
  { id: 1, type: 'fill', pronom: 'qui', sentence: "C'est un appartement ____ est très lumineux.", options: ['qui', 'que', 'où'], feedback: "'Qui' est le sujet du verbe 'est'." },
  { id: 2, type: 'fill', pronom: 'que', sentence: "Voici la cuisine ____ j'ai repeinte en blanc.", options: ['qui', 'que', 'où'], feedback: "'Que' est le complément d'objet direct de 'j'ai repeinte'." },
  { id: 3, type: 'fill', pronom: 'où', sentence: "C'est le quartier ____ j'habite depuis un an.", options: ['qui', 'que', 'où'], feedback: "'Où' exprime ici le lieu (le quartier)." },
  { id: 4, type: 'fill', pronom: 'qui', sentence: "Je cherche un colocataire ____ est ordonné.", options: ['qui', 'que', 'où'], feedback: "'Qui' remplace le sujet 'un colocataire'." },
  { id: 5, type: 'fill', pronom: 'que', sentence: "C'est une annonce ____ j'ai vue sur Internet.", options: ['qui', 'que', 'où'], feedback: "'Que' remplace l'antécédent 'une annonce' (C.O.D)." },
  { id: 6, type: 'fill', pronom: 'où', sentence: "La ville ____ je loue ce studio est calme.", options: ['qui', 'que', 'où'], feedback: "'Où' indique la situation géographique." },
  { id: 7, type: 'fill', pronom: 'qui', sentence: "Le salon est la pièce ____ coûte la plus chère.", options: ['qui', 'que', 'où'], feedback: "'Qui' fait l'action de coûter (sujet)." },
  { id: 8, type: 'fill', pronom: 'que', sentence: "Les meubles ____ tu as choisis sont modernes.", options: ['qui', 'que', 'où'], feedback: "'Que' est placé avant le sujet 'tu'." },
  { id: 9, type: 'fill', pronom: 'où', sentence: "C'est l'étage ____ se trouve ma chambre.", options: ['qui', 'que', 'où'], feedback: "'Où' introduit le lieu où se trouve la chambre." },
  { id: 10, type: 'fill', pronom: 'qui', sentence: "Il y a des voisins ____ font trop de bruit.", options: ['qui', 'que', 'où'], feedback: "'Qui' est le sujet du verbe 'font'." },
  { id: 11, type: 'fill', pronom: 'que', sentence: "La caution ____ j'ai payée est énorme.", options: ['qui', 'que', 'où'], feedback: "'Que' remplace 'la caution'." },
  { id: 12, type: 'fill', pronom: 'où', sentence: "Le placard ____ je range mes vêtements est petit.", options: ['qui', 'que', 'où'], feedback: "'Où' désigne l'espace de rangement." },
  { id: 13, type: 'fill', pronom: 'qui', sentence: "C'est un immeuble ____ a été construit en 1920.", options: ['qui', 'que', 'où'], feedback: "'Qui' est sujet de la forme passive." },
  { id: 14, type: 'fill', pronom: 'que', sentence: "Le contrat ____ nous avons signé est clair.", options: ['qui', 'que', 'où'], feedback: "'Que' est suivi du sujet 'nous'." },
  { id: 15, type: 'fill', pronom: 'où', sentence: "Le jour ____ j'ai emménagé, il pleuvait.", options: ['qui', 'que', 'où'], feedback: "'Où' exprime ici le temps (le moment)." },
  { id: 16, type: 'fill', pronom: 'qui', sentence: "Le propriétaire ____ loue ce garage est sympa.", options: ['qui', 'que', 'où'], feedback: "'Qui' est le sujet qui fait l'action de louer." },
  { id: 17, type: 'fill', pronom: 'que', sentence: "C'est une colocation ____ je recommande.", options: ['qui', 'que', 'où'], feedback: "'Que' remplace l'objet direct." },
  { id: 18, type: 'fill', pronom: 'où', sentence: "Le village ____ se situe cette maison est loin.", options: ['qui', 'que', 'où'], feedback: "'Où' indique la localisation." },
  { id: 19, type: 'fill', pronom: 'qui', sentence: "C'est la fenêtre ____ donne sur le jardin.", options: ['qui', 'que', 'où'], feedback: "'Qui' est sujet du verbe 'donne'." },
  { id: 20, type: 'fill', pronom: 'que', sentence: "Les photos ____ vous voyez sont réelles.", options: ['qui', 'que', 'où'], feedback: "'Que' est suivi du sujet 'vous'." },
];

const App = () => {
  const [currentStep, setCurrentStep] = useState('welcome');
  const [currentIndex, setCurrentIndex] = useState(0);
  const [score, setScore] = useState(0);
  const [showFeedback, setShowFeedback] = useState(false);
  const [selectedOption, setSelectedOption] = useState(null);
  const [isCorrect, setIsCorrect] = useState(false);
  const [xp, setXp] = useState(0);
  const [showRules, setShowRules] = useState(false);

    const handleStart = () => {
    setCurrentIndex(0);
    setScore(0);
    setXp(0);
    setShowRules(false);
    setCurrentStep('quiz');
  };

    const handleBackToDashboard = () => {
    // Reset session stats when leaving
    setCurrentIndex(0);
    setScore(0);
    setXp(0);

    // Reset UI state
    setShowRules(false);
    setShowFeedback(false);
    setSelectedOption(null);
    setIsCorrect(false);

    setCurrentStep('welcome');
  };

  const handleAnswer = (option) => {
    if (showFeedback) return;

    setSelectedOption(option);
    const correct = option === exercises[currentIndex].pronom;
    setIsCorrect(correct);
    setShowFeedback(true);

    if (correct) {
      setScore(score + 1);
      setXp(xp + 50);
    }
  };

  const handleNext = () => {
    setShowFeedback(false);
    setSelectedOption(null);
    if (currentIndex < exercises.length - 1) {
      setCurrentIndex(currentIndex + 1);
    } else {
      setCurrentStep('results');
    }
  };

  const progress = ((currentIndex + 1) / exercises.length) * 100;

  return (
    <div className="min-h-screen bg-slate-50 text-slate-900 font-sans p-4 md:p-8 flex flex-col items-center justify-center">
      <div className="max-w-3xl w-full bg-white rounded-3xl shadow-xl overflow-hidden border border-slate-100">

        {/* En-tête */}
        <div className="bg-indigo-600 p-6 text-white flex justify-between items-center">
          <div className="flex items-center gap-2">
            <div className="bg-white/20 p-2 rounded-lg">
              <Home size={24} />
            </div>
            <h1 className="text-xl font-bold tracking-tight">Pronomsrel <span className="text-indigo-200 font-normal text-sm ml-2">v1.2</span></h1>
          </div>
          <div className="flex items-center gap-4 text-sm font-medium">
            <div className="flex items-center gap-1 bg-white/10 px-3 py-1 rounded-full border border-white/20">
              <Star size={16} className="text-yellow-300 fill-yellow-300" />
              <span>{xp} XP</span>
            </div>
          </div>
        </div>

        <div className="p-6 md:p-8">
          {currentStep === 'welcome' && (
            <div className="space-y-8 py-4">
              <div className="text-center space-y-4">
                <div className="inline-block p-4 bg-indigo-50 rounded-full text-indigo-600">
                  <BookOpen size={40} />
                </div>
                <h2 className="text-3xl font-extrabold text-slate-800">Prêt pour le défi ?</h2>
                <p className="text-slate-600 max-w-lg mx-auto">
                  Apprenez à relier des phrases sur le thème du <b>logement</b> en utilisant correctement les pronoms relatifs.
                </p>
              </div>

              {/* TABLEAU DE BORD DES RÈGLES */}
              <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
                <div className="bg-blue-50 p-5 rounded-2xl border border-blue-100 transition-hover hover:shadow-md">
                  <div className="flex items-center gap-2 text-blue-700 font-bold mb-3 uppercase text-xs tracking-wider">
                    <span className="bg-blue-600 text-white w-5 h-5 flex items-center justify-center rounded-full text-[10px]">1</span>
                    Qui (Sujet)
                  </div>
                  <p className="text-sm text-blue-900 mb-2 font-medium italic">Remplace le sujet de la phrase.</p>
                  <div className="text-xs bg-white/60 p-2 rounded-lg border border-blue-200/50">
                    <p className="font-bold text-blue-800">Structure :</p>
                    <p className="mb-1 underline">Qui + Verbe</p>
                    <p className="text-slate-500 italic">Ex : La chambre <span className="text-blue-600 font-bold">qui</span> est libre.</p>
                  </div>
                </div>

                <div className="bg-emerald-50 p-5 rounded-2xl border border-emerald-100 transition-hover hover:shadow-md">
                  <div className="flex items-center gap-2 text-emerald-700 font-bold mb-3 uppercase text-xs tracking-wider">
                    <span className="bg-emerald-600 text-white w-5 h-5 flex items-center justify-center rounded-full text-[10px]">2</span>
                    Que (O.D.)
                  </div>
                  <p className="text-sm text-emerald-900 mb-2 font-medium italic">Remplace l'objet direct.</p>
                  <div className="text-xs bg-white/60 p-2 rounded-lg border border-emerald-200/50">
                    <p className="font-bold text-emerald-800">Structure :</p>
                    <p className="mb-1 underline">Que + Sujet (je, tu...)</p>
                    <p className="text-slate-500 italic">Ex : La maison <span className="text-emerald-600 font-bold">que</span> j'adore.</p>
                  </div>
                </div>

                <div className="bg-amber-50 p-5 rounded-2xl border border-amber-100 transition-hover hover:shadow-md">
                  <div className="flex items-center gap-2 text-amber-700 font-bold mb-3 uppercase text-xs tracking-wider">
                    <span className="bg-amber-600 text-white w-5 h-5 flex items-center justify-center rounded-full text-[10px]">3</span>
                    Où (Lieu/Temps)
                  </div>
                  <p className="text-sm text-amber-900 mb-2 font-medium italic">Indique le lieu ou le moment.</p>
                  <div className="text-xs bg-white/60 p-2 rounded-lg border border-amber-200/50">
                    <p className="font-bold text-amber-800">Usage :</p>
                    <p className="mb-1 underline">Indique une position.</p>
                    <p className="text-slate-500 italic">Ex : Le studio <span className="text-amber-600 font-bold">où</span> il habite.</p>
                  </div>
                </div>
              </div>

              <div className="bg-indigo-50/50 p-4 rounded-xl border border-indigo-100 flex items-start gap-3">
                <Lightbulb className="text-indigo-500 shrink-0 mt-1" size={20} />
                <p className="text-sm text-indigo-700 leading-snug italic">
                  <b>Astuce :</b> Si le mot suivant est un <b>verbe</b>, utilisez "qui". S'il s'agit d'un <b>sujet</b> (nom ou pronom), utilisez "que". S'il s'agit d'un <b>lieu</b>, utilisez "où".
                </p>
              </div>

                            {/* Bouton principal */}
              <button 
                onClick={handleStart}
                className="w-full py-5 bg-indigo-600 hover:bg-indigo-700 text-white rounded-2xl font-bold text-xl shadow-lg shadow-indigo-100 transition-all transform hover:scale-[1.02] active:scale-95 flex items-center justify-center gap-3"
              >
                Commencer l'entraînement <ArrowRight size={24} />
              </button>
            </div>
          )}

          {currentStep === 'quiz' && (
            <div className="space-y-8">
                            {/* Barre de progression */}
              <div className="space-y-2">
                <div className="flex justify-between text-xs font-bold text-slate-400 uppercase tracking-wider">
                  <span>Progression {currentIndex + 1} / {exercises.length}</span>
                  <span>{Math.round(progress)}%</span>
                </div>
                <div className="h-3 w-full bg-slate-100 rounded-full overflow-hidden">
                  <div 
                    className="h-full bg-indigo-500 transition-all duration-500 ease-out"
                    style={{ width: `${progress}%` }}
                  />
                </div>
              </div>

              <div className="flex justify-between items-center">
                <button
                  type="button"
                  onClick={handleBackToDashboard}
                  className="px-4 py-3 rounded-xl font-bold text-sm bg-white border border-slate-200 text-slate-600 hover:border-rose-400 hover:bg-rose-50 hover:text-rose-700 transition-all flex items-center gap-2"
                >
                  <Home size={18} />
                  Quitter
                </button>

                <button
                  type="button"
                  onClick={() => setShowRules(true)}
                  className="px-4 py-3 rounded-xl font-bold text-sm bg-white border border-slate-200 text-slate-600 hover:border-indigo-400 hover:bg-indigo-50 hover:text-indigo-700 transition-all flex items-center gap-2"
                  aria-label="Voir le résumé des règles"
                >
                  <Info size={18} />
                  Voir le résumé
                </button>
              </div>

              {/* Carte de question */}
              <div className="bg-slate-50 border border-slate-200 p-10 rounded-3xl relative overflow-hidden">
                <div className="absolute top-0 left-0 w-1.5 h-full bg-indigo-400"></div>
                <p className="text-2xl text-center font-medium text-slate-800 leading-relaxed">
                  {exercises[currentIndex].sentence.split('____')[0]}
                  <span className="mx-2 px-6 py-1 border-b-4 border-indigo-500 bg-indigo-100 text-indigo-800 rounded-xl animate-pulse font-bold">
                    ?
                  </span>
                  {exercises[currentIndex].sentence.split('____')[1]}
                </p>
              </div>

              {/* Options de réponse */}
              <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
                {exercises[currentIndex].options.map((option) => (
                  <button
                    key={option}
                    disabled={showFeedback}
                    onClick={() => handleAnswer(option)}
                    className={`p-6 rounded-2xl font-bold text-xl border-2 transition-all transform hover:-translate-y-1 active:translate-y-0 shadow-sm
                      ${selectedOption === option
                        ? (isCorrect ? 'bg-emerald-50 border-emerald-500 text-emerald-700' : 'bg-rose-50 border-rose-500 text-rose-700')
                        : 'bg-white border-slate-200 text-slate-600 hover:border-indigo-400 hover:bg-indigo-50 hover:text-indigo-700'}
                      ${showFeedback && option === exercises[currentIndex].pronom && !isCorrect ? 'border-emerald-500 bg-emerald-50 text-emerald-700' : ''}
                    `}
                  >
                    {option}
                  </button>
                ))}
              </div>

              {/* Feedback */}
              {showFeedback && (
                <div className={`p-6 rounded-2xl flex flex-col md:flex-row items-center gap-6 animate-in fade-in slide-in-from-bottom-4 duration-300 ${isCorrect ? 'bg-emerald-50 border border-emerald-200' : 'bg-rose-50 border border-rose-200'}`}>
                  <div className="shrink-0">
                    {isCorrect ? <CheckCircle className="text-emerald-500" size={48} /> : <XCircle className="text-rose-500" size={48} />}
                  </div>
                  <div className="flex-1 text-center md:text-left">
                    <p className={`font-black text-xl mb-1 ${isCorrect ? 'text-emerald-800' : 'text-rose-800'}`}>
                      {isCorrect ? 'Bravo !' : 'Attention !'}
                    </p>
                    <p className={`text-sm font-medium ${isCorrect ? 'text-emerald-700' : 'text-rose-700'}`}>
                      {exercises[currentIndex].feedback}
                    </p>
                  </div>
                  <button
                    onClick={handleNext}
                    className={`px-8 py-4 rounded-xl font-bold text-white transition-all shadow-lg active:scale-95 ${isCorrect ? 'bg-emerald-600 hover:bg-emerald-700' : 'bg-rose-600 hover:bg-rose-700'}`}
                  >
                    Suivant
                  </button>
                </div>
              )}
            </div>
          )}

          {currentStep === 'results' && (
            <div className="text-center space-y-8 py-4">
              <div className="relative inline-block">
                <div className="p-8 bg-indigo-50 rounded-full text-indigo-600 shadow-inner">
                  <Trophy size={80} />
                </div>
                <div className="absolute -top-2 -right-2 bg-yellow-400 text-white p-2 rounded-full shadow-lg border-4 border-white animate-bounce">
                  <Star size={24} fill="white" />
                </div>
              </div>

              <div className="space-y-2">
                <h2 className="text-4xl font-black text-slate-800 tracking-tight">C'est génial !</h2>
                <p className="text-slate-400 font-bold text-sm uppercase tracking-[0.3em]">Résultats de la session</p>
              </div>

              <div className="grid grid-cols-2 gap-4 max-w-sm mx-auto">
                <div className="bg-slate-50 p-6 rounded-3xl border border-slate-100">
                  <p className="text-4xl font-black text-indigo-600">{score}/{exercises.length}</p>
                  <p className="text-xs text-slate-500 font-bold uppercase mt-1 tracking-wider">Score</p>
                </div>
                <div className="bg-slate-50 p-6 rounded-3xl border border-slate-100">
                  <p className="text-4xl font-black text-amber-500">+{xp}</p>
                  <p className="text-xs text-slate-500 font-bold uppercase mt-1 tracking-wider">Total XP</p>
                </div>
              </div>

              <div className="flex flex-col md:flex-row gap-4 justify-center">
                <button
                  onClick={handleStart}
                  className="w-full md:w-auto px-10 py-5 bg-slate-800 hover:bg-slate-900 text-white rounded-2xl font-bold text-lg shadow-xl transition-all transform hover:scale-105 active:scale-95 flex items-center justify-center gap-2"
                >
                  <RefreshCw size={20} /> Recommencer le quiz
                </button>

                <button
                  onClick={handleBackToDashboard}
                  className="w-full md:w-auto px-10 py-5 bg-white hover:bg-slate-50 text-slate-800 rounded-2xl font-bold text-lg shadow-sm border-2 border-slate-200 transition-all transform hover:scale-105 active:scale-95 flex items-center justify-center gap-2"
                >
                  <Home size={20} /> Retour au dashboard
                </button>
              </div>
            </div>
          )}
        </div>
        {/* Modal résumé des règles (accessible pendant le quiz) */}
        {showRules && (
          <div className="fixed inset-0 z-50 flex items-center justify-center p-4">
            <div
              className="absolute inset-0 bg-slate-900/40"
              onClick={() => setShowRules(false)}
            />
            <div className="relative w-full max-w-3xl bg-white rounded-3xl shadow-2xl border border-slate-100 overflow-hidden">
              <div className="p-5 bg-indigo-600 text-white flex items-center justify-between">
                <div className="flex items-center gap-2 font-bold">
                  <Info size={18} />
                  Résumé des règles
                </div>
                <button
                  type="button"
                  onClick={() => setShowRules(false)}
                  className="px-4 py-2 rounded-xl bg-white/15 hover:bg-white/20 border border-white/20 font-bold text-sm"
                >
                  Fermer
                </button>
              </div>

              <div className="p-6 md:p-8 space-y-4">
                <div className="grid grid-cols-1 md:grid-cols-3 gap-4">
                  <div className="bg-blue-50 p-5 rounded-2xl border border-blue-100 transition-hover hover:shadow-md">
                    <div className="flex items-center gap-2 text-blue-700 font-bold mb-3 uppercase text-xs tracking-wider">
                      <span className="bg-blue-600 text-white w-5 h-5 flex items-center justify-center rounded-full text-[10px]">1</span>
                      Qui (Sujet)
                    </div>
                    <p className="text-sm text-blue-900 mb-2 font-medium italic">Remplace le sujet de la phrase.</p>
                    <div className="text-xs bg-white/60 p-2 rounded-lg border border-blue-200/50">
                      <p className="font-bold text-blue-800">Structure :</p>
                      <p className="mb-1 underline">Qui + Verbe</p>
                      <p className="text-slate-500 italic">Ex : La chambre <span className="text-blue-600 font-bold">qui</span> est libre.</p>
                    </div>
                  </div>

                  <div className="bg-emerald-50 p-5 rounded-2xl border border-emerald-100 transition-hover hover:shadow-md">
                    <div className="flex items-center gap-2 text-emerald-700 font-bold mb-3 uppercase text-xs tracking-wider">
                      <span className="bg-emerald-600 text-white w-5 h-5 flex items-center justify-center rounded-full text-[10px]">2</span>
                      Que (O.D.)
                    </div>
                    <p className="text-sm text-emerald-900 mb-2 font-medium italic">Remplace l'objet direct.</p>
                    <div className="text-xs bg-white/60 p-2 rounded-lg border border-emerald-200/50">
                      <p className="font-bold text-emerald-800">Structure :</p>
                      <p className="mb-1 underline">Que + Sujet (je, tu...)</p>
                      <p className="text-slate-500 italic">Ex : La maison <span className="text-emerald-600 font-bold">que</span> j'adore.</p>
                    </div>
                  </div>

                  <div className="bg-amber-50 p-5 rounded-2xl border border-amber-100 transition-hover hover:shadow-md">
                    <div className="flex items-center gap-2 text-amber-700 font-bold mb-3 uppercase text-xs tracking-wider">
                      <span className="bg-amber-600 text-white w-5 h-5 flex items-center justify-center rounded-full text-[10px]">3</span>
                      Où (Lieu/Temps)
                    </div>
                    <p className="text-sm text-amber-900 mb-2 font-medium italic">Indique le lieu ou le moment.</p>
                    <div className="text-xs bg-white/60 p-2 rounded-lg border border-amber-200/50">
                      <p className="font-bold text-amber-800">Usage :</p>
                      <p className="mb-1 underline">Indique une position.</p>
                      <p className="text-slate-500 italic">Ex : Le studio <span className="text-amber-600 font-bold">où</span> il habite.</p>
                    </div>
                  </div>
                </div>

                <div className="bg-indigo-50/50 p-4 rounded-xl border border-indigo-100 flex items-start gap-3">
                  <Lightbulb className="text-indigo-500 shrink-0 mt-1" size={20} />
                  <p className="text-sm text-indigo-700 leading-snug italic">
                    <b>Astuce :</b> Si le mot suivant est un <b>verbe</b>, utilisez "qui". S'il s'agit d'un <b>sujet</b> (nom ou pronom), utilisez "que". S'il s'agit d'un <b>lieu</b>, utilisez "où".
                  </p>
                </div>
              </div>
            </div>
          </div>
        )}

        <div className="p-4 bg-slate-50 border-t border-slate-100 text-center text-[10px] text-slate-400 uppercase tracking-[0.2em] font-medium">
          Outil FLE • Thématique Le Logement • 2026
        </div>
      </div>
    </div>
  );
};

export default App;
