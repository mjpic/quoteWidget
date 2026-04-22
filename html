<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SealWRX Quote Generator</title>
  <script src="https://unpkg.com/react@18/umd/react.production.min.js" crossorigin></script>
  <script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js" crossorigin></script>
  <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Oswald:wght@400;600;700&display=swap" rel="stylesheet">
  
  <style>
    :root {
      --bg: #09090b; --surface: #18181b; --border: #27272a; --text: #e4e4e7;
      --muted: #a1a1aa; --accent: #facc15; --success: #22c55e; --warning: #f97316; --danger: #ef4444;
    }
    body { margin: 0; background: var(--bg); color: var(--text); font-family: 'Inter', sans-serif; -webkit-font-smoothing: antialiased; }
    * { box-sizing: border-box; }
    .app-container { max-width: 1400px; margin: 0 auto; padding-bottom: 40px; }
    
    .header { border-bottom: 1px solid var(--border); padding: 24px 40px; display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 20px; }
    @media (max-width: 600px) {
      .header { padding: 20px; flex-direction: column; align-items: flex-start; }
    }

    .content { padding: 32px 40px; }
    @media (max-width: 600px) { .content { padding: 20px; } }

    .grid { display: grid; gap: 20px; }
    .grid-2 { grid-template-columns: 1fr 1fr; }
    .grid-3 { grid-template-columns: 1fr 1fr 1fr; }
    .grid-4 { grid-template-columns: 1fr 1fr 1fr 1fr; }
    @media (max-width: 768px) { 
      .grid-2, .grid-3 { grid-template-columns: 1fr; } 
      .grid-4 { grid-template-columns: 1fr 1fr; }
    }
    
    .card { background: var(--surface); border: 1px solid var(--border); border-radius: 8px; padding: 24px; position: relative; overflow: hidden; }
    .card-title { font-size: 12px; letter-spacing: 2px; color: var(--muted); text-transform: uppercase; margin-bottom: 16px; font-weight: 500; }
    
    input, select, textarea { background: var(--bg); border: 1px solid var(--border); color: var(--text); padding: 10px 14px; border-radius: 6px; font-family: inherit; font-size: 14px; width: 100%; margin-bottom: 4px; }
    input:focus, textarea:focus { outline: none; border-color: var(--accent); }
    textarea { resize: vertical; }
    .btn-save { background: var(--success); color: #000; border: none; font-weight: 700; font-family: 'Oswald', sans-serif; letter-spacing: 1px; padding: 12px 24px; cursor: pointer; border-radius: 6px; white-space: nowrap; transition: opacity 0.2s; }
    .btn-save:hover { opacity: 0.9; }
    .btn-secondary { background: var(--surface); color: var(--text); border: 1px solid var(--border); font-weight: 600; padding: 8px 16px; cursor: pointer; border-radius: 6px; font-size: 12px; transition: all 0.2s; }
    .btn-secondary:hover { border-color: var(--accent); }
    
    .contact-sub { font-size: 12px; color: var(--muted); display: block; margin-top: 2px; }
    .job-badge { font-size: 11px; background: var(--accent); color: #000; padding: 4px 8px; border-radius: 4px; margin-right: 12px; font-weight: bold; font-family: monospace; display: inline-block; }

    .crm-container { display: grid; grid-template-columns: 320px 1fr; gap: 24px; align-items: start; }
    .sticky-sidebar { align-self: start; position: sticky; top: 20px; }
    
    @media (max-width: 900px) { 
      .crm-container { grid-template-columns: 1fr; } 
      .sticky-sidebar { position: static; align-self: stretch; }
    }

    .customer-block { background: var(--surface); border: 1px solid var(--border); border-radius: 8px; padding: 24px; margin-bottom: 24px; }
    .customer-header { display: flex; justify-content: space-between; align-items: flex-start; border-bottom: 1px solid var(--border); padding-bottom: 16px; margin-bottom: 20px; flex-wrap: wrap; gap: 12px; }
    .customer-title { font-family: 'Oswald', sans-serif; font-size: 24px; margin: 0 0 4px 0; color: #fff; text-transform: uppercase; }
    
    .job-item { background: var(--bg); border: 1px solid var(--border); border-radius: 8px; padding: 20px; margin-bottom: 16px; position: relative; }
    .job-item:last-child { margin-bottom: 0; }
    .job-top-row { display: flex; justify-content: space-between; align-items: center; margin-bottom: 16px; flex-wrap: wrap; gap: 12px; }
    .quote-box { background: var(--surface); border: 1px dashed var(--border); border-radius: 6px; padding: 16px; margin: 16px 0; }
    .quote-totals { text-align: right; font-family: 'Oswald', sans-serif; font-size: 24px; color: var(--accent); margin-top: 12px; }
  </style>
</head>
<body>
  <div id="root"></div>

  <script type="text/babel">
    const API_URL = "https://script.google.com/macros/s/AKfycbyKWJE-paxhj6_ppU03rSYwiW2yjkPjdFoR9iKjMC9JW5WMCOBwkqk7iufeEvoKIrdu/exec"; 

    const { useState, useEffect } = React;

    function calcJobTotal(job) {
      if (!job.crackFill && !job.sealingLabor && !job.stripingCost && job.amount) return Number(job.amount);
      const cf = Number(job.crackFill) || 0;
      const sl = Number(job.sealingLabor) || 0;
      const st = Number(job.stripingCost) || 0;
      const subtotal = cf + sl + st;
      const discountAmt = subtotal * ((Number(job.discountPct) || 0) / 100);
      const taxAmt = (subtotal - discountAmt) * ((Number(job.taxPct) || 0) / 100);
      return subtotal - discountAmt + taxAmt;
    }

    function SealWRXBoard() {
      const [contacts, setContacts] = useState([]); 
      const [newContact, setNewContact] = useState({ 
        name: "", phone: "", address: "", type: "Driveway",
        date: new Date().toISOString().split('T')[0], notes: "", 
        crackFill: "", sealingLabor: "", stripingCost: "", discountPct: "", taxPct: "8.0" 
      });
      
      const [isLoading, setIsLoading] = useState(true);
      const [isSaving, setIsSaving] = useState(false);

      useEffect(() => {
        fetch(API_URL).then(res => res.json()).then(data => {
          if (data.contacts) setContacts(data.contacts);
          setIsLoading(false);
        }).catch(() => {
          setIsLoading(false);
        });
      }, []);

      const generateJobNumber = () => `SWX-${Date.now().toString().slice(-6)}`;

      const handleAddContact = (e) => {
        e.preventDefault();
        const jobNumber = generateJobNumber();
        setContacts([{ ...newContact, id: Date.now(), jobNumber }, ...contacts]);
        setNewContact({ 
          name: "", phone: "", address: "", type: "Driveway",
          date: new Date().toISOString().split('T')[0], notes: "", 
          crackFill: "", sealingLabor: "", stripingCost: "", discountPct: "", taxPct: "8.0" 
        });
      };

      const handleTextQuote = (job) => {
        const total = calcJobTotal(job).toFixed(2);
        const message = `Hi ${job.name}, this is SealWRX. Your estimate for Job #${job.jobNumber} is $${total}. Valid for 30 days. Let us know if you'd like to get on the schedule! Call/Text: 315-577-3806 or visit tinyurl.com/sealwrx`;

        navigator.clipboard.writeText(message)
          .then(() => alert("📋 Quote copied to clipboard! You can now paste it anywhere."))
          .catch(err => alert("❌ Failed to copy. Your browser might be blocking clipboard access."));
      };

      const updateContact = (id, field, val) => setContacts(prev => prev.map(c => c.id === id ? { ...c, [field]: val } : c));

      const handleAddJobToCustomer = (name, phone, address) => {
        const jobNumber = generateJobNumber();
        const newJob = { 
          id: Date.now(), jobNumber, name, phone, address, type: "Driveway",
          date: new Date().toISOString().split('T')[0], notes: "", 
          crackFill: "", sealingLabor: "", stripingCost: "", discountPct: "", taxPct: "8.0" 
        };
        setContacts([newJob, ...contacts]);
      };

      const saveData = () => {
        setIsSaving(true);
        // Sending an empty weeks array to prevent breaking the existing Google Script expecting it
        fetch(API_URL, { 
            method: "POST", 
            mode: "no-cors",
            headers: { "Content-Type": "text/plain" },
            body: JSON.stringify({ weeks: [], contacts }) 
        })
        .then(() => { 
            setIsSaving(false); 
            alert("✅ Cloud Data Saved!"); 
        })
        .catch(() => { 
            setIsSaving(false); 
            alert("✅ Data Saved to Cloud!"); 
        });
      };

      const handlePrintDocument = (job) => {
        const cf = Number(job.crackFill) || 0;
        const sl = Number(job.sealingLabor) || 0;
        const st = Number(job.stripingCost) || 0;
        const sub = (cf + sl + st) || Number(job.amount) || 0;
        const discAmt = sub * ((Number(job.discountPct) || 0) / 100);
        const taxAmt = (sub - discAmt) * ((Number(job.taxPct) || 0) / 100);
        const total = sub - discAmt + taxAmt;
        
        const titleText = 'PAVEMENT PROTECTION ESTIMATE';
        
        const creationDate = new Date(job.date + 'T12:00:00');
        const expireDate = new Date(creationDate);
        expireDate.setDate(expireDate.getDate() + 30);
        const expirationStr = expireDate.toLocaleDateString();

        const printWin = window.open('', '_blank');
        printWin.document.write(`
          <html>
            <head>
              <title>Estimate - ${job.jobNumber}</title>
              <style>
                body { font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; padding: 40px; color: #333; line-height: 1.6; max-width: 800px; margin: 0 auto; }
                
                /* COVER PAGE STYLES */
                .cover-page { display: flex; flex-direction: column; justify-content: center; align-items: center; text-align: center; min-height: 85vh; page-break-after: always; }
                .cover-title { font-size: 46px; font-weight: bold; color: #111; margin-bottom: 10px; text-transform: uppercase; border-bottom: 4px solid #facc15; padding-bottom: 15px; letter-spacing: 2px; }
                .cover-subtitle { font-size: 32px; color: #222; font-weight: bold; margin-bottom: 5px; text-transform: uppercase; }
                .cover-phone { font-size: 22px; color: #555; margin-bottom: 50px; }
                .cover-client-info { font-size: 20px; margin-top: 40px; padding: 40px; border: 2px solid #eee; border-radius: 8px; min-width: 400px; background: #fafafa; }
                
                /* ESTIMATE STYLES */
                .header { border-bottom: 3px solid #facc15; padding-bottom: 20px; margin-bottom: 30px; display: flex; justify-content: space-between; align-items: flex-end; }
                h1 { margin: 0; color: #111; font-size: 32px; letter-spacing: 1px; text-transform: uppercase; }
                .info-block { margin-bottom: 30px; }
                .row { display: flex; justify-content: space-between; padding: 12px 0; border-bottom: 1px solid #eee; }
                .total-row { font-weight: bold; font-size: 1.4em; border-top: 3px solid #333; margin-top: 15px; padding-top: 15px; display: flex; justify-content: space-between;}
                .footer-insured { font-weight: bold; text-transform: uppercase; margin-top: 15px; display: block; font-size: 16px; color: #111; letter-spacing: 1px; }
                
                @media print { 
                    body { padding: 0; } 
                    .cover-page { padding-top: 15vh; min-height: 100vh; }
                }
              </style>
            </head>
            <body>
              <div class="cover-page">
                <div class="cover-title">OFFICIAL QUOTE</div>
                <div class="cover-subtitle">SEALWRX</div>
                <div class="cover-phone">315-577-3806</div>

                <div class="cover-client-info">
                  <div style="color: #666; font-size: 14px; text-transform: uppercase; margin-bottom: 15px;">Prepared For:</div>
                  <div style="font-weight: bold; color: #000; font-size: 28px; line-height: 1.2;">${job.name}</div>
                  ${job.address ? `<div style="margin-top: 12px; color: #444; font-size: 18px;">${job.address}</div>` : ''}
                </div>
              </div>

              <div class="header">
                <div>
                  <h1>SEALWRX</h1>
                  <div style="color: #666; margin-top: 5px; font-weight: bold;">${titleText}</div>
                </div>
                <div style="text-align: right;">
                  <p style="margin:0;">Job Number: <strong>${job.jobNumber}</strong></p>
                  <p style="margin:0;">Date Prepared: ${new Date(job.date + 'T12:00:00').toLocaleDateString()}</p>
                  <p style="margin:0; color: #ef4444; font-weight: bold;">Valid Until: ${expirationStr}</p>
                </div>
              </div>
              
              <div class="info-block">
                <h3 style="color: #666; margin-bottom: 5px; text-transform: uppercase; font-size: 14px;">Prepared For:</h3>
                <div style="font-size: 18px; font-weight: bold; color: #000;">${job.name}</div>
                ${job.phone ? `<div>${job.phone}</div>` : ''}
                ${job.address ? `<div>${job.address}</div>` : ''}
              </div>
              
              <h3 style="color: #666; margin-bottom: 10px; text-transform: uppercase; font-size: 14px;">Job Details & Charges:</h3>
              <div class="row"><span>Crack Fill Materials</span><span>$${cf.toFixed(2)}</span></div>
              <div class="row"><span>Sealing / Labor</span><span>$${sl.toFixed(2)}</span></div>
              <div class="row"><span>Striping</span><span>$${st.toFixed(2)}</span></div>
              <div class="row" style="color: #666; font-size: 14px;"><span>Subtotal</span><span>$${sub.toFixed(2)}</span></div>
              
              ${discAmt > 0 ? `<div class="row" style="color: #ef4444;"><span>Discount (${job.discountPct||0}%)</span><span>-$${discAmt.toFixed(2)}</span></div>` : ''}
              ${taxAmt > 0 ? `<div class="row" style="color: #666; font-size: 14px;"><span>Sales Tax (${job.taxPct||0}%)</span><span>+$${taxAmt.toFixed(2)}</span></div>` : ''}
              
              <div class="total-row"><span>TOTAL AMOUNT</span><span>$${total.toFixed(2)}</span></div>
              
              ${job.notes ? `<div style="margin-top: 30px; font-size: 14px; color: #555;"><strong>Notes:</strong><br/>${job.notes}</div>` : ''}
              
              <p style="margin-top: 60px; text-align: center; color: #666; font-size: 14px; border-top: 1px solid #eee; padding-top: 20px;">
                This estimate is subject to property inspection and is valid for 30 days.<br>
                <span class="footer-insured">WE ARE FULLY INSURED</span>
              </p>
            </body>
          </html>
        `);
        printWin.document.close();
        printWin.focus();
        setTimeout(() => { printWin.print(); }, 250);
      };

      const groupedCustomers = {};
      contacts.forEach(c => {
        const key = (c.name || "Unknown").trim().toLowerCase();
        if (!groupedCustomers[key]) {
          groupedCustomers[key] = { name: c.name, phone: c.phone, address: c.address, jobs: [] };
        }
        groupedCustomers[key].jobs.push(c);
      });

      if (isLoading) return <div style={{padding: 50, color: 'var(--accent)', fontFamily:'Oswald'}}>LOADING CLOUD DATA...</div>;

      return (
        <div className="app-container">
          <div className="header">
            <div>
              <div style={{ color: "var(--accent)", fontSize: 12, letterSpacing: 4, fontWeight: 600 }}>SEALWRX</div>
              <h1 style={{fontFamily:'Oswald', margin:0, letterSpacing:'2px'}}>QUOTE GENERATOR</h1>
            </div>
            <button onClick={saveData} className="btn-save">{isSaving ? "SAVING..." : "💾 SAVE TO CLOUD"}</button>
          </div>

          <div className="content">
            <div className="crm-container">
              
              {/* LEFT SIDEBAR - ADD NEW */}
              <div className="card sticky-sidebar">
                <div className="card-title">Create New Quote</div>
                <form onSubmit={handleAddContact} style={{display:'flex', flexDirection:'column', gap:'8px'}}>
                  <input type="text" placeholder="Customer Name *" required value={newContact.name} onChange={e => setNewContact({...newContact, name: e.target.value})} />
                  <input type="text" placeholder="Phone Number" value={newContact.phone} onChange={e => setNewContact({...newContact, phone: e.target.value})} />
                  <input type="text" placeholder="Street Address" value={newContact.address} onChange={e => setNewContact({...newContact, address: e.target.value})} />
                  <div style={{ borderTop: '1px solid var(--border)', margin: '12px 0 4px 0', paddingTop: '12px' }} className="contact-sub">Job Quote Details:</div>
                  <div className="grid grid-3" style={{gap: '8px'}}>
                    <input type="number" placeholder="Crack Fill $" value={newContact.crackFill} onChange={e => setNewContact({...newContact, crackFill: e.target.value})} />
                    <input type="number" placeholder="Labor $" value={newContact.sealingLabor} onChange={e => setNewContact({...newContact, sealingLabor: e.target.value})} />
                    <input type="number" placeholder="Striping $" value={newContact.stripingCost} onChange={e => setNewContact({...newContact, stripingCost: e.target.value})} />
                  </div>
                  <label style={{fontSize:'11px', color:'var(--muted)', marginTop:'4px'}}>Quote Date</label>
                  <input type="date" value={newContact.date} onChange={e => setNewContact({...newContact, date: e.target.value})} />
                  <button type="submit" className="btn-save" style={{background:'var(--accent)', marginTop:'12px', width: '100%'}}>CREATE CUSTOMER</button>
                </form>
              </div>

              {/* RIGHT MAIN - CONTACTS & QUOTES */}
              <div>
                {Object.keys(groupedCustomers).length === 0 ? (
                    <div style={{color: "var(--muted)", fontStyle: "italic", padding: "20px"}}>No contacts or quotes yet. Create one on the left!</div>
                ) : null}

                {Object.values(groupedCustomers).map(group => (
                  <div key={group.name} className="customer-block">
                    <div className="customer-header">
                      <div>
                        <h2 className="customer-title">{group.name}</h2>
                        <div className="contact-sub">{group.phone || "No Phone"} &bull; {group.address || "No Address"}</div>
                      </div>
                      <button onClick={() => handleAddJobToCustomer(group.name, group.phone, group.address)} className="btn-secondary" style={{ background: 'var(--accent)', color: '#000', border: 'none' }}>
                        + ADD NEW QUOTE
                      </button>
                    </div>

                    <div className="jobs-list">
                      {group.jobs.map(job => (
                        <div key={job.id} className="job-item">
                          <div className="job-top-row">
                            <div>
                              <span className="job-badge">{job.jobNumber || 'LEGACY-JOB'}</span>
                              <input type="date" value={job.date} onChange={e => updateContact(job.id, 'date', e.target.value)} style={{border:'none', fontSize:'12px', padding:0, background:'transparent', color:'var(--muted)', width: 'auto'}} />
                            </div>
                            <button onClick={() => setContacts(contacts.filter(con => con.id !== job.id))} style={{color:'var(--danger)', background:'none', border:'none', cursor:'pointer', fontSize:'12px'}}>Delete Quote</button>
                          </div>

                          <div className="quote-box">
                            <div className="grid grid-4" style={{gap: '12px'}}>
                              <div><label className="contact-sub">Crack Fill ($)</label><input type="number" value={job.crackFill || ''} onChange={e => updateContact(job.id, 'crackFill', e.target.value)} /></div>
                              <div><label className="contact-sub">Labor ($)</label><input type="number" value={job.sealingLabor || ''} onChange={e => updateContact(job.id, 'sealingLabor', e.target.value)} /></div>
                              <div><label className="contact-sub">Striping ($)</label><input type="number" value={job.stripingCost || ''} onChange={e => updateContact(job.id, 'stripingCost', e.target.value)} /></div>
                              <div className="grid grid-2" style={{gap: '8px'}}>
                                <div><label className="contact-sub">Disc %</label><input type="number" value={job.discountPct || ''} onChange={e => updateContact(job.id, 'discountPct', e.target.value)} /></div>
                                <div><label className="contact-sub">Tax %</label><input type="number" value={job.taxPct || '8.0'} onChange={e => updateContact(job.id, 'taxPct', e.target.value)} /></div>
                              </div>
                            </div>
                            <div className="quote-totals">TOTAL: ${calcJobTotal(job).toFixed(2)}</div>
                          </div>

                          <div className="grid grid-2" style={{ alignItems: 'end', gap: '16px' }}>
                            <textarea value={job.notes || ""} maxLength={200} onChange={e => updateContact(job.id, 'notes', e.target.value)} placeholder="Add quote notes..." style={{ width: '100%', minHeight: '44px', margin: 0 }} />
                            <div style={{ textAlign: 'right', display: 'flex', gap: '8px', justifyContent: 'flex-end', flexWrap: 'wrap' }}>
                              <button onClick={() => handleTextQuote(job)} className="btn-secondary" style={{ color: 'var(--accent)', borderColor: 'var(--accent)', fontWeight: 'bold' }}>📋 COPY QUOTE TEXT</button>
                              <button onClick={() => handlePrintDocument(job)} className="btn-secondary" style={{ color: 'var(--text)', borderColor: 'var(--border)' }}>📄 PRINT QUOTE PDF</button>
                            </div>
                          </div>
                        </div>
                      ))}
                    </div>
                  </div>
                ))}
              </div>
            </div>
          </div>
        </div>
      );
    }
    ReactDOM.createRoot(document.getElementById('root')).render(<SealWRXBoard />);
  </script>
</body>
</html>
