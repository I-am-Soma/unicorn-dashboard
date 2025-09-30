import React, { useState, useEffect } from 'react';
import { BarChart, Bar, PieChart, Pie, Cell, XAxis, YAxis, CartesianGrid, Tooltip, Legend, ResponsiveContainer } from 'recharts';
import { AlertCircle, Users, MapPin, TrendingUp, Activity, CheckCircle } from 'lucide-react';

const Dashboard = () => {
  const [activeView, setActiveView] = useState('overview');
  const [animatedCount, setAnimatedCount] = useState(0);
  const [isLive, setIsLive] = useState(false);
  const [responses, setResponses] = useState([]);
  const [totalCount, setTotalCount] = useState(30);
  const [soundEnabled, setSoundEnabled] = useState(true);
  const [toasts, setToasts] = useState([]);
  const [showManualForm, setShowManualForm] = useState(false);
  const [manualEntry, setManualEntry] = useState({
    name: '',
    category: 'Tienda',
    colonia: 'Centro',
    response: 'Seguridad'
  });

  // Datos de prioridades (ahora dinámico)
  const [priorityData, setPriorityData] = useState([
    { name: 'Seguridad', value: 11, percent: 36.67, color: '#ef4444' },
    { name: 'Empleo', value: 7, percent: 23.33, color: '#3b82f6' },
    { name: 'Infraestructura', value: 7, percent: 23.33, color: '#f59e0b' },
    { name: 'Salud', value: 5, percent: 16.67, color: '#10b981' }
  ]);

  // Datos por colonia (ahora dinámico)
  const [coloniaData, setColoniaData] = useState([
    { name: 'Centro', total: 8, seguridad: 5, empleo: 0, salud: 2, infra: 1 },
    { name: 'Partido Romero', total: 5, seguridad: 2, empleo: 0, salud: 0, infra: 3 },
    { name: 'Tecnológico', total: 4, seguridad: 0, empleo: 3, salud: 1, infra: 0 },
    { name: 'Benito Juárez', total: 3, seguridad: 1, empleo: 0, salud: 2, infra: 0 },
    { name: 'San Lorenzo', total: 3, seguridad: 1, empleo: 0, salud: 1, infra: 1 },
    { name: 'La Cuesta', total: 3, seguridad: 1, empleo: 1, salud: 0, infra: 1 },
    { name: 'Infonavit', total: 3, seguridad: 0, empleo: 2, salud: 0, infra: 1 },
    { name: 'Industrial', total: 1, seguridad: 1, empleo: 0, salud: 0, infra: 0 }
  ]);

  // Negocios recientes (últimos 6) - dinámico
  const [recentBusinesses, setRecentBusinesses] = useState([
    { id: 'F010', name: 'Farmacia Moderna', category: 'Farmacia', response: 'Infraestructura', colonia: 'Partido Romero', time: '10:29' },
    { id: 'F009', name: 'Farmacia Santa María', category: 'Farmacia', response: 'Empleo', colonia: 'Infonavit', time: '10:28' },
    { id: 'F008', name: 'Farmacia del Centro', category: 'Farmacia', response: 'Seguridad', colonia: 'Centro', time: '10:27' },
    { id: 'M010', name: 'Mecánica Central', category: 'Taller', response: 'Seguridad', colonia: 'Centro', time: '10:26' },
    { id: 'M009', name: 'Taller Elite', category: 'Taller', response: 'Seguridad', colonia: 'Partido Romero', time: '10:25' },
    { id: 'F007', name: 'Farmacia Comunitaria Ortiz', category: 'Farmacia', response: 'Salud', colonia: 'San Lorenzo', time: '10:24' }
  ]);

  // Pool de negocios para simular
  const businessPool = [
    { id: 'S001', name: 'Abarrotes San José', category: 'Tienda', colonia: 'Centro' },
    { id: 'S002', name: 'La Tiendita de Rosa', category: 'Tienda', colonia: 'Centro' },
    { id: 'S003', name: 'Mini Market La 16', category: 'Tienda', colonia: 'Partido Romero' },
    { id: 'M001', name: 'Taller El Ángel', category: 'Taller', colonia: 'Industrial' },
    { id: 'F001', name: 'Farmacia Vida', category: 'Farmacia', colonia: 'Centro' },
    { id: 'F002', name: 'Farmacia San Pablo', category: 'Farmacia', colonia: 'Benito Juárez' }
  ];

  const responseTypes = ['Seguridad', 'Empleo', 'Salud', 'Infraestructura'];
  
  const colonias = ['Centro', 'Partido Romero', 'Tecnológico', 'Benito Juárez', 'San Lorenzo', 'La Cuesta', 'Infonavit', 'Industrial'];
  const categories = ['Tienda', 'Taller', 'Farmacia'];

  // Función para mostrar toast
  const showToast = (message, type = 'success') => {
    const id = Date.now();
    const newToast = { id, message, type };
    setToasts(prev => [...prev, newToast]);
    
    setTimeout(() => {
      setToasts(prev => prev.filter(t => t.id !== id));
    }, 4000);
  };

  // Función para reproducir sonido
  const playSound = () => {
    if (soundEnabled) {
      const audioContext = new (window.AudioContext || window.webkitAudioContext)();
      const oscillator = audioContext.createOscillator();
      const gainNode = audioContext.createGain();
      
      oscillator.connect(gainNode);
      gainNode.connect(audioContext.destination);
      
      oscillator.frequency.value = 800;
      oscillator.type = 'sine';
      
      gainNode.gain.setValueAtTime(0.3, audioContext.currentTime);
      gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.3);
      
      oscillator.start(audioContext.currentTime);
      oscillator.stop(audioContext.currentTime + 0.3);
    }
  };

  // Función para agregar nueva respuesta
  const addNewResponse = (customData = null) => {
    let businessData, responseData, coloniaData;
    
    if (customData) {
      businessData = {
        id: `M${Date.now().toString().slice(-3)}`,
        name: customData.name,
        category: customData.category,
        colonia: customData.colonia
      };
      responseData = customData.response;
      coloniaData = customData.colonia;
    } else {
      const randomBusiness = businessPool[Math.floor(Math.random() * businessPool.length)];
      businessData = randomBusiness;
      responseData = responseTypes[Math.floor(Math.random() * responseTypes.length)];
      coloniaData = randomBusiness.colonia;
    }
    
    const now = new Date();
    const timeStr = `${now.getHours()}:${now.getMinutes().toString().padStart(2, '0')}`;
    
    const newEntry = {
      id: businessData.id,
      name: businessData.name,
      category: businessData.category,
      response: responseData,
      colonia: coloniaData,
      time: timeStr
    };

    playSound();
    showToast(`Nueva respuesta de ${businessData.name}: ${responseData}`, 'success');
    
    setRecentBusinesses(prev => [newEntry, ...prev.slice(0, 5)]);
    setTotalCount(prev => prev + 1);

    // Actualizar conteos de prioridades
    setPriorityData(prev => {
      const updated = [...prev];
      const index = updated.findIndex(p => p.name === responseData);
      if (index !== -1) {
        updated[index].value += 1;
        const total = updated.reduce((sum, item) => sum + item.value, 0);
        updated.forEach(item => {
          item.percent = parseFloat(((item.value / total) * 100).toFixed(2));
        });
      }
      return updated;
    });

    // Actualizar datos por colonia
    setColoniaData(prev => {
      const updated = [...prev];
      const coloniaIndex = updated.findIndex(c => c.name === coloniaData);
      if (coloniaIndex !== -1) {
        updated[coloniaIndex].total += 1;
        const responseKey = responseData.toLowerCase() === 'infraestructura' ? 'infra' : responseData.toLowerCase();
        if (updated[coloniaIndex][responseKey] !== undefined) {
          updated[coloniaIndex][responseKey] += 1;
        }
      } else {
        // Agregar nueva colonia si no existe
        const newColonia = {
          name: coloniaData,
          total: 1,
          seguridad: responseData === 'Seguridad' ? 1 : 0,
          empleo: responseData === 'Empleo' ? 1 : 0,
          salud: responseData === 'Salud' ? 1 : 0,
          infra: responseData === 'Infraestructura' ? 1 : 0
        };
        updated.push(newColonia);
      }
      return updated.sort((a, b) => b.total - a.total);
    });
  };

  // Función para enviar entrada manual
  const handleManualSubmit = (e) => {
    e.preventDefault();
    if (manualEntry.name.trim() === '') {
      showToast('Por favor ingresa el nombre del negocio', 'error');
      return;
    }
    
    addNewResponse(manualEntry);
    setManualEntry({ name: '', category: 'Tienda', colonia: 'Centro', response: 'Seguridad' });
    setShowManualForm(false);
  };

  // Animación de contador
  useEffect(() => {
    if (animatedCount < totalCount) {
      const timer = setTimeout(() => setAnimatedCount(animatedCount + 1), 50);
      return () => clearTimeout(timer);
    }
  }, [animatedCount, totalCount]);

  // Simular "en vivo"
  useEffect(() => {
    const interval = setInterval(() => setIsLive(prev => !prev), 1000);
    return () => clearInterval(interval);
  }, []);

  const StatCard = ({ icon: Icon, label, value, subtext, color }) => (
    <div className="bg-white rounded-xl shadow-lg p-6 border-l-4" style={{ borderColor: color }}>
      <div className="flex items-center justify-between">
        <div>
          <p className="text-sm text-gray-500 font-medium">{label}</p>
          <p className="text-3xl font-bold mt-2" style={{ color }}>{value}</p>
          {subtext && <p className="text-xs text-gray-400 mt-1">{subtext}</p>}
        </div>
        <Icon className="w-12 h-12 opacity-20" style={{ color }} />
      </div>
    </div>
  );

  return (
    <div className="min-h-screen bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900 p-6">
      {/* Toast Notifications */}
      <div className="fixed top-4 right-4 z-50 space-y-2">
        {toasts.map(toast => (
          <div
            key={toast.id}
            className={`px-6 py-4 rounded-lg shadow-2xl border-2 transform transition-all duration-300 animate-slideIn ${
              toast.type === 'success' 
                ? 'bg-green-500 border-green-400 text-white' 
                : 'bg-red-500 border-red-400 text-white'
            }`}
            style={{ animation: 'slideIn 0.3s ease-out' }}
          >
            <div className="flex items-center gap-3">
              <span className="text-2xl">{toast.type === 'success' ? '✅' : '⚠️'}</span>
              <p className="font-semibold">{toast.message}</p>
            </div>
          </div>
        ))}
      </div>

      {/* Modal para entrada manual */}
      {showManualForm && (
        <div className="fixed inset-0 bg-black/60 backdrop-blur-sm z-40 flex items-center justify-center p-4">
          <div className="bg-white rounded-2xl shadow-2xl max-w-md w-full p-6 transform transition-all">
            <div className="flex items-center justify-between mb-6">
              <h3 className="text-2xl font-bold text-gray-800">📝 Agregar Respuesta Manual</h3>
              <button
                onClick={() => setShowManualForm(false)}
                className="text-gray-400 hover:text-gray-600 text-2xl"
              >
                ✕
              </button>
            </div>
            
            <form onSubmit={handleManualSubmit} className="space-y-4">
              <div>
                <label className="block text-sm font-semibold text-gray-700 mb-2">
                  Nombre del Negocio *
                </label>
                <input
                  type="text"
                  value={manualEntry.name}
                  onChange={(e) => setManualEntry({...manualEntry, name: e.target.value})}
                  placeholder="Ej: Tienda Don José"
                  className="w-full px-4 py-3 border-2 border-gray-300 rounded-lg focus:border-purple-600 focus:outline-none"
                  required
                />
              </div>

              <div>
                <label className="block text-sm font-semibold text-gray-700 mb-2">
                  Categoría
                </label>
                <select
                  value={manualEntry.category}
                  onChange={(e) => setManualEntry({...manualEntry, category: e.target.value})}
                  className="w-full px-4 py-3 border-2 border-gray-300 rounded-lg focus:border-purple-600 focus:outline-none"
                >
                  {categories.map(cat => (
                    <option key={cat} value={cat}>{cat}</option>
                  ))}
                </select>
              </div>

              <div>
                <label className="block text-sm font-semibold text-gray-700 mb-2">
                  Colonia
                </label>
                <select
                  value={manualEntry.colonia}
                  onChange={(e) => setManualEntry({...manualEntry, colonia: e.target.value})}
                  className="w-full px-4 py-3 border-2 border-gray-300 rounded-lg focus:border-purple-600 focus:outline-none"
                >
                  {colonias.map(col => (
                    <option key={col} value={col}>{col}</option>
                  ))}
                </select>
              </div>

              <div>
                <label className="block text-sm font-semibold text-gray-700 mb-2">
                  Respuesta (Prioridad)
                </label>
                <select
                  value={manualEntry.response}
                  onChange={(e) => setManualEntry({...manualEntry, response: e.target.value})}
                  className="w-full px-4 py-3 border-2 border-gray-300 rounded-lg focus:border-purple-600 focus:outline-none"
                >
                  {responseTypes.map(resp => (
                    <option key={resp} value={resp}>{resp}</option>
                  ))}
                </select>
              </div>

              <div className="flex gap-3 pt-4">
                <button
                  type="button"
                  onClick={() => setShowManualForm(false)}
                  className="flex-1 px-4 py-3 bg-gray-200 text-gray-700 rounded-lg font-semibold hover:bg-gray-300 transition-colors"
                >
                  Cancelar
                </button>
                <button
                  type="submit"
                  className="flex-1 px-4 py-3 bg-purple-600 text-white rounded-lg font-semibold hover:bg-purple-700 transition-colors"
                >
                  ✓ Agregar
                </button>
              </div>
            </form>
          </div>
        </div>
      )}

      {/* Header */}
      <div className="max-w-7xl mx-auto mb-8">
        <div className="flex items-center justify-between">
          <div>
            <h1 className="text-4xl font-bold text-white mb-2">
              Unicorn AI <span className="text-purple-400">Dashboard</span>
            </h1>
            <p className="text-gray-300">Sistema de Escucha Ciudadana - Demo en Vivo</p>
          </div>
          <div className="flex items-center gap-3">
            <div className="flex items-center gap-2 bg-green-500/20 px-4 py-2 rounded-lg border border-green-500/30">
              <div className={`w-3 h-3 rounded-full bg-green-400 ${isLive ? 'animate-pulse' : ''}`}></div>
              <span className="text-green-300 font-semibold">EN VIVO</span>
            </div>
            <div className="text-right">
              <p className="text-gray-400 text-sm">Ciudad Juárez, Chihuahua</p>
              <p className="text-white font-semibold">30 Sep 2025, 10:30 AM</p>
            </div>
          </div>
        </div>
      </div>

      <div className="max-w-7xl mx-auto">
        {/* Tabs */}
        <div className="flex gap-2 mb-6">
          {[
            { id: 'overview', icon: '📊', label: 'Resumen General' },
            { id: 'colonias', icon: '🗺️', label: 'Por Colonia' },
            { id: 'mapa', icon: '🌍', label: 'Mapa Interactivo' },
            { id: 'live', icon: '⚡', label: 'Tiempo Real' }
          ].map(view => (
            <button
              key={view.id}
              onClick={() => {
                setActiveView(view.id);
                playSound();
              }}
              className={`px-6 py-3 rounded-lg font-semibold transition-all ${
                activeView === view.id
                  ? 'bg-purple-600 text-white shadow-lg'
                  : 'bg-white/10 text-gray-300 hover:bg-white/20'
              }`}
            >
              {view.icon} {view.label}
            </button>
          ))}
          <button
            onClick={() => setSoundEnabled(!soundEnabled)}
            className="ml-auto px-4 py-3 rounded-lg bg-white/10 text-gray-300 hover:bg-white/20 transition-all"
            title={soundEnabled ? 'Silenciar' : 'Activar sonido'}
          >
            {soundEnabled ? '🔊' : '🔇'}
          </button>
        </div>

        {/* Overview View */}
        {activeView === 'overview' && (
          <div className="space-y-6">
            {/* KPIs */}
            <div className="grid grid-cols-4 gap-6">
              <StatCard 
                icon={Users} 
                label="Negocios Indexados" 
                value={animatedCount}
                subtext="10 tiendas, 10 talleres, 10 farmacias"
                color="#8b5cf6"
              />
              <StatCard 
                icon={CheckCircle} 
                label="Respuestas Recibidas" 
                value={animatedCount}
                subtext="Tasa de respuesta: 100%"
                color="#10b981"
              />
              <StatCard 
                icon={MapPin} 
                label="Colonias Cubiertas" 
                value="8"
                subtext="Centro, Partido Romero, Tecnológico..."
                color="#f59e0b"
              />
              <StatCard 
                icon={TrendingUp} 
                label="Prioridad #1" 
                value="Seguridad"
                subtext="36.67% de menciones"
                color="#ef4444"
              />
            </div>

            {/* Charts */}
            <div className="grid grid-cols-2 gap-6">
              {/* Pie Chart */}
              <div className="bg-white rounded-xl shadow-lg p-6">
                <h3 className="text-xl font-bold text-gray-800 mb-4">Prioridades Ciudadanas</h3>
                <ResponsiveContainer width="100%" height={300}>
                  <PieChart>
                    <Pie
                      data={priorityData}
                      cx="50%"
                      cy="50%"
                      labelLine={false}
                      label={({ name, percent }) => `${name} ${percent}%`}
                      outerRadius={100}
                      fill="#8884d8"
                      dataKey="value"
                    >
                      {priorityData.map((entry, index) => (
                        <Cell key={`cell-${index}`} fill={entry.color} />
                      ))}
                    </Pie>
                    <Tooltip />
                  </PieChart>
                </ResponsiveContainer>
                <div className="mt-4 grid grid-cols-2 gap-3">
                  {priorityData.map(item => (
                    <div key={item.name} className="flex items-center gap-2">
                      <div className="w-4 h-4 rounded" style={{ backgroundColor: item.color }}></div>
                      <span className="text-sm text-gray-600">{item.name}: <strong>{item.value}</strong></span>
                    </div>
                  ))}
                </div>
              </div>

              {/* Bar Chart */}
              <div className="bg-white rounded-xl shadow-lg p-6">
                <h3 className="text-xl font-bold text-gray-800 mb-4">Respuestas por Colonia</h3>
                <ResponsiveContainer width="100%" height={300}>
                  <BarChart data={coloniaData}>
                    <CartesianGrid strokeDasharray="3 3" />
                    <XAxis dataKey="name" angle={-45} textAnchor="end" height={100} fontSize={12} />
                    <YAxis />
                    <Tooltip />
                    <Bar dataKey="total" fill="#8b5cf6" radius={[8, 8, 0, 0]} />
                  </BarChart>
                </ResponsiveContainer>
              </div>
            </div>

            {/* Insight Box */}
            <div className="bg-gradient-to-r from-red-500/20 to-red-600/20 border border-red-500/30 rounded-xl p-6">
              <div className="flex items-start gap-4">
                <AlertCircle className="w-8 h-8 text-red-400 flex-shrink-0 mt-1" />
                <div>
                  <h3 className="text-xl font-bold text-white mb-2">🎯 Insight Clave</h3>
                  <p className="text-gray-200 text-lg">
                    La <strong>Seguridad</strong> es la prioridad dominante con <strong>36.67%</strong> de las menciones. 
                    La <strong>Col. Centro</strong> concentra el mayor volumen (8 respuestas) con 5 menciones de seguridad.
                    Recomendación: <strong>Brigada de seguridad piloto en Centro</strong> con seguimiento en 2 semanas.
                  </p>
                </div>
              </div>
            </div>
          </div>
        )}

        {/* Colonias View */}
        {activeView === 'colonias' && (
          <div className="space-y-6">
            <div className="bg-white rounded-xl shadow-lg p-6">
              <h3 className="text-2xl font-bold text-gray-800 mb-6">Análisis Detallado por Colonia</h3>
              <ResponsiveContainer width="100%" height={400}>
                <BarChart data={coloniaData} layout="vertical">
                  <CartesianGrid strokeDasharray="3 3" />
                  <XAxis type="number" />
                  <YAxis dataKey="name" type="category" width={120} />
                  <Tooltip />
                  <Legend />
                  <Bar dataKey="seguridad" fill="#ef4444" name="Seguridad" />
                  <Bar dataKey="empleo" fill="#3b82f6" name="Empleo" />
                  <Bar dataKey="salud" fill="#10b981" name="Salud" />
                  <Bar dataKey="infra" fill="#f59e0b" name="Infraestructura" />
                </BarChart>
              </ResponsiveContainer>
            </div>

            {/* Tabla detallada */}
            <div className="bg-white rounded-xl shadow-lg overflow-hidden">
              <table className="w-full">
                <thead className="bg-purple-600 text-white">
                  <tr>
                    <th className="px-6 py-4 text-left font-semibold">Colonia</th>
                    <th className="px-6 py-4 text-center font-semibold">🔴 Seguridad</th>
                    <th className="px-6 py-4 text-center font-semibold">🔵 Empleo</th>
                    <th className="px-6 py-4 text-center font-semibold">🟢 Salud</th>
                    <th className="px-6 py-4 text-center font-semibold">🟠 Infraestructura</th>
                    <th className="px-6 py-4 text-center font-semibold">Total</th>
                    <th className="px-6 py-4 text-center font-semibold">Prioridad</th>
                  </tr>
                </thead>
                <tbody>
                  {coloniaData.map((col, idx) => {
                    const max = Math.max(col.seguridad, col.empleo, col.salud, col.infra);
                    const priority = max === col.seguridad ? '🔴 Seguridad' : 
                                   max === col.empleo ? '🔵 Empleo' :
                                   max === col.salud ? '🟢 Salud' : '🟠 Infraestructura';
                    return (
                      <tr key={idx} className={idx % 2 === 0 ? 'bg-gray-50' : 'bg-white'}>
                        <td className="px-6 py-4 font-semibold text-gray-800">{col.name}</td>
                        <td className="px-6 py-4 text-center">{col.seguridad}</td>
                        <td className="px-6 py-4 text-center">{col.empleo}</td>
                        <td className="px-6 py-4 text-center">{col.salud}</td>
                        <td className="px-6 py-4 text-center">{col.infra}</td>
                        <td className="px-6 py-4 text-center font-bold">{col.total}</td>
                        <td className="px-6 py-4 text-center text-sm font-semibold">{priority}</td>
                      </tr>
                    );
                  })}
                </tbody>
              </table>
            </div>
          </div>
        )}

        {/* Mapa View */}
        {activeView === 'mapa' && (
          <div className="space-y-6">
            <div className="bg-white rounded-xl shadow-lg p-6">
              <h3 className="text-2xl font-bold text-gray-800 mb-6">Mapa de Calor por Colonia</h3>
              <div className="relative w-full h-[500px] bg-gradient-to-br from-slate-100 to-slate-200 rounded-lg overflow-hidden">
                {/* Mapa simulado con colonias */}
                <div className="absolute inset-0 grid grid-cols-3 grid-rows-3 gap-2 p-4">
                  {coloniaData.slice(0, 9).map((col, idx) => {
                    const maxTotal = Math.max(...coloniaData.map(c => c.total));
                    const intensity = (col.total / maxTotal);
                    
                    // Colores más intensos basados en el total
                    let bgStyle = {};
                    if (intensity >= 0.66) {
                      bgStyle = { backgroundColor: `rgba(239, 68, 68, ${0.7 + intensity * 0.3})` }; // rojo intenso
                    } else if (intensity >= 0.33) {
                      bgStyle = { backgroundColor: `rgba(245, 158, 11, ${0.6 + intensity * 0.4})` }; // naranja intenso
                    } else {
                      bgStyle = { backgroundColor: `rgba(251, 191, 36, ${0.5 + intensity * 0.5})` }; // amarillo intenso
                    }
                    
                    const maxIssue = Math.max(col.seguridad, col.empleo, col.salud, col.infra);
                    const topIssue = maxIssue === col.seguridad ? '🔴 Seguridad' :
                                    maxIssue === col.empleo ? '🔵 Empleo' :
                                    maxIssue === col.salud ? '🟢 Salud' : '🟠 Infraestructura';
                    
                    return (
                      <div
                        key={idx}
                        className="rounded-lg p-4 flex flex-col justify-between hover:scale-105 transition-transform cursor-pointer border-2 border-white shadow-lg"
                        style={bgStyle}
                      >
                        <div>
                          <p className="font-bold text-white text-lg drop-shadow-md">{col.name}</p>
                          <p className="text-white text-sm font-semibold drop-shadow">{topIssue}</p>
                        </div>
                        <div className="mt-2">
                          <p className="text-white text-2xl font-bold drop-shadow-lg">{col.total}</p>
                          <p className="text-white text-xs drop-shadow">respuestas</p>
                        </div>
                      </div>
                    );
                  })}
                </div>
                
                {/* Leyenda */}
                <div className="absolute bottom-4 right-4 bg-white rounded-lg p-4 shadow-lg">
                  <p className="font-bold text-gray-800 mb-2">Intensidad de Respuestas</p>
                  <div className="flex items-center gap-2 mb-1">
                    <div className="w-6 h-6 bg-red-500 rounded"></div>
                    <span className="text-sm text-gray-600">Alta (6-8)</span>
                  </div>
                  <div className="flex items-center gap-2 mb-1">
                    <div className="w-6 h-6 bg-orange-500 rounded"></div>
                    <span className="text-sm text-gray-600">Media (3-5)</span>
                  </div>
                  <div className="flex items-center gap-2">
                    <div className="w-6 h-6 bg-yellow-500 rounded"></div>
                    <span className="text-sm text-gray-600">Baja (1-2)</span>
                  </div>
                </div>
              </div>
            </div>

            {/* Análisis geográfico */}
            <div className="grid grid-cols-2 gap-6">
              <div className="bg-gradient-to-br from-red-500/20 to-red-600/20 border border-red-500/30 rounded-xl p-6">
                <h4 className="text-xl font-bold text-white mb-3">🎯 Zona de Mayor Prioridad</h4>
                <p className="text-3xl font-bold text-white mb-2">{coloniaData[0]?.name}</p>
                <p className="text-gray-200">
                  Con <strong>{coloniaData[0]?.total} respuestas</strong>, esta zona requiere atención inmediata.
                  Prioridad dominante: <strong className="text-red-300">
                    {Math.max(coloniaData[0]?.seguridad, coloniaData[0]?.empleo, coloniaData[0]?.salud, coloniaData[0]?.infra) === coloniaData[0]?.seguridad ? 'Seguridad' :
                     Math.max(coloniaData[0]?.seguridad, coloniaData[0]?.empleo, coloniaData[0]?.salud, coloniaData[0]?.infra) === coloniaData[0]?.empleo ? 'Empleo' :
                     Math.max(coloniaData[0]?.seguridad, coloniaData[0]?.empleo, coloniaData[0]?.salud, coloniaData[0]?.infra) === coloniaData[0]?.salud ? 'Salud' : 'Infraestructura'}
                  </strong>
                </p>
              </div>
              
              <div className="bg-gradient-to-br from-blue-500/20 to-blue-600/20 border border-blue-500/30 rounded-xl p-6">
                <h4 className="text-xl font-bold text-white mb-3">📊 Cobertura Geográfica</h4>
                <p className="text-3xl font-bold text-white mb-2">{coloniaData.length} colonias</p>
                <p className="text-gray-200">
                  Representación distribuida en toda la ciudad. La muestra cubre 
                  <strong className="text-blue-300"> {((coloniaData.length / 15) * 100).toFixed(0)}%</strong> de las colonias objetivo.
                </p>
              </div>
            </div>
          </div>
        )}

        {/* Live Feed View */}
        {activeView === 'live' && (
          <div className="space-y-6">
            <div className="bg-white rounded-xl shadow-lg p-6">
              <div className="flex items-center justify-between mb-6">
                <h3 className="text-2xl font-bold text-gray-800">Feed de Respuestas en Tiempo Real</h3>
                <div className="flex items-center gap-3">
                  <Activity className="w-6 h-6 text-purple-600 animate-pulse" />
                  <button
                    onClick={() => setShowManualForm(true)}
                    className="px-4 py-2 bg-green-600 text-white rounded-lg font-semibold hover:bg-green-700 transition-colors flex items-center gap-2"
                  >
                    <span>✏️</span> Manual
                  </button>
                  <button
                    onClick={() => addNewResponse()}
                    className="px-4 py-2 bg-purple-600 text-white rounded-lg font-semibold hover:bg-purple-700 transition-colors flex items-center gap-2"
                  >
                    <span>🎲</span> Aleatorio
                  </button>
                </div>
              </div>
              <div className="space-y-3">
                {recentBusinesses.map((biz, idx) => (
                  <div 
                    key={idx}
                    className="flex items-center justify-between p-4 bg-gradient-to-r from-purple-50 to-white rounded-lg border border-purple-100 hover:shadow-md transition-shadow"
                    style={{ animation: `fadeIn 0.5s ease-out ${idx * 0.1}s both` }}
                  >
                    <div className="flex items-center gap-4 flex-1">
                      <div className="w-12 h-12 bg-purple-600 rounded-full flex items-center justify-center text-white font-bold">
                        {biz.category === 'Farmacia' ? '💊' : biz.category === 'Taller' ? '🔧' : '🏪'}
                      </div>
                      <div>
                        <p className="font-bold text-gray-800">{biz.name}</p>
                        <p className="text-sm text-gray-500">{biz.id} • {biz.category} • {biz.colonia}</p>
                      </div>
                    </div>
                    <div className="flex items-center gap-4">
                      <div className="text-right">
                        <p className="font-semibold text-purple-600">{biz.response}</p>
                        <p className="text-xs text-gray-400">{biz.time}</p>
                      </div>
                      <CheckCircle className="w-6 h-6 text-green-500" />
                    </div>
                  </div>
                ))}
              </div>
            </div>

            {/* Propuesta de Acción */}
            <div className="bg-gradient-to-r from-green-500/20 to-green-600/20 border border-green-500/30 rounded-xl p-6">
              <h3 className="text-2xl font-bold text-white mb-4">🚀 Propuesta de Piloto</h3>
              <div className="grid grid-cols-3 gap-4 mb-4">
                <div className="bg-white/10 rounded-lg p-4">
                  <p className="text-green-300 font-semibold mb-2">Duración</p>
                  <p className="text-2xl font-bold text-white">6 semanas</p>
                </div>
                <div className="bg-white/10 rounded-lg p-4">
                  <p className="text-green-300 font-semibold mb-2">Meta de Mensajes</p>
                  <p className="text-2xl font-bold text-white">1,000 / colonia</p>
                </div>
                <div className="bg-white/10 rounded-lg p-4">
                  <p className="text-green-300 font-semibold mb-2">Colonias Piloto</p>
                  <p className="text-2xl font-bold text-white">Centro + 2 más</p>
                </div>
              </div>
              <p className="text-gray-200">
                <strong>Entregables:</strong> Dashboard semanal actualizado, 2 mapas de calor comparativos (inicio/final), 
                y coordinación de 1 acción piloto por tema prioritario (brigada de seguridad, jornada de empleo, clínica móvil).
              </p>
            </div>
          </div>
        )}
      </div>

      <style>{`
        @keyframes fadeIn {
          from { opacity: 0; transform: translateY(20px); }
          to { opacity: 1; transform: translateY(0); }
        }
        @keyframes slideIn {
          from { 
            opacity: 0; 
            transform: translateX(100px) scale(0.8);
          }
          to { 
            opacity: 1; 
            transform: translateX(0) scale(1);
          }
        }
      `}</style>
    </div>
  );
};

export default Dashboard;
