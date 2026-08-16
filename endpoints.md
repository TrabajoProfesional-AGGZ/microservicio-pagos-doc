---
layout: default
title: Endpoints
nav_order: 2
---

# 🔌 Endpoints

En esta sección se listan los endpoints disponibles en el microservicio de pagos.

Esta página sirve como referencia estática para garantizar el acceso a los contratos de la pasarela de pagos y notificaciones de Mercado Pago de forma rápida y clara.

## Listado de Endpoints

A continuación, haz clic en cada bloque para desplegar los detalles de la petición, parámetros y respuestas.

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/api/v1/pagos/health</code> - Health Check
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>health_check_api_v1_pagos_health_get</code></p>
    
    <p>Endpoint para verificar que el microservicio está funcionando correctamente.</p>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
      <li><strong>Content-Type:</strong> <code>application/json</code></li>
    </ul>

    <strong>Ejemplo de respuesta:</strong>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{}</span>
</code></pre></div></div>

  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #28a745; margin-bottom: 5px;">
    <strong style="color: #28a745;">POST</strong> <code>/api/v1/pagos/webhook</code> - Recibir Webhook Mercadopago
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>recibir_webhook_mercadopago_api_v1_pagos_webhook_post</code></p>
    
    <p>Recibe las notificaciones IPN/Webhooks enviadas por Mercado Pago para actualizar estados de transacciones.</p>

    <h3>Cuerpo de la Petición (Request Body)</h3>
    <p><strong>Content-Type:</strong> <code>application/json</code> (Requerido)</p>

    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"action"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
  </span><span class="nl">"api_version"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
  </span><span class="nl">"data"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="nl">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="nl">"date_created"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
  </span><span class="nl">"id"</span><span class="p">:</span><span class="w"> </span><span class="integer">0</span><span class="p">,</span><span class="w">
  </span><span class="nl">"live_mode"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span><span class="p">,</span><span class="w">
  </span><span class="nl">"type"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
  </span><span class="nl">"user_id"</span><span class="p">:</span><span class="w"> </span><span class="integer">0</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{}</span>
</code></pre></div></div>

    <p><strong>Código:</strong> <code>422 Unprocessable Entity</code></p>
    <ul>
      <li><strong>Descripción:</strong> Validation Error</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"detail"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="nl">"loc"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"string"</span><span class="p">,</span><span class="w"> </span><span class="integer">0</span><span class="p">],</span><span class="w">
      </span><span class="nl">"msg"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"type"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #28a745; margin-bottom: 5px;">
    <strong style="color: #28a745;">POST</strong> <code>/api/v1/pagos/procesar</code> - Procesar Pago Endpoint
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>procesar_pago_endpoint_api_v1_pagos_procesar_post</code></p>
    
    <p>Recibe el token de tarjeta desde el Checkout Brick y ejecuta el cobro de forma directa.</p>

    <h3>Cuerpo de la Petición (Request Body)</h3>
    <p><strong>Content-Type:</strong> <code>application/json</code> (Requerido)</p>

    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"token"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
  </span><span class="nl">"transaction_amount"</span><span class="p">:</span><span class="w"> </span><span class="mf">0.0</span><span class="p">,</span><span class="w">
  </span><span class="nl">"installments"</span><span class="p">:</span><span class="w"> </span><span class="integer">0</span><span class="p">,</span><span class="w">
  </span><span class="nl">"payment_method_id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
  </span><span class="nl">"issuer_id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string (o null)"</span><span class="p">,</span><span class="w">
  </span><span class="nl">"payer"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
    </span><span class="nl">"email"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
    </span><span class="nl">"identification"</span><span class="p">:</span><span class="w"> </span><span class="p">{}</span><span class="w">
  </span><span class="p">},</span><span class="w">
  </span><span class="nl">"id_item"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string (uuid4)"</span><span class="p">,</span><span class="w">
  </span><span class="nl">"tipo_item"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{}</span>
</code></pre></div></div>

    <p><strong>Código:</strong> <code>422 Unprocessable Entity</code></p>
    <ul>
      <li><strong>Descripción:</strong> Validation Error</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"detail"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
    </span><span class="p">{</span><span class="w">
      </span><span class="nl">"loc"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="s2">"string"</span><span class="p">,</span><span class="w"> </span><span class="integer">0</span><span class="p">],</span><span class="w">
      </span><span class="nl">"msg"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="p">,</span><span class="w">
      </span><span class="nl">"type"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="w">
    </span><span class="p">}</span><span class="w">
  </span><span class="p">]</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

  </div>
</details>
