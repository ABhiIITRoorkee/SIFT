
<h1>SIFT: Source-Supported Functional Intent Mining for Android Library Recommendation</h1>

<p><strong>Function-aware library recommendation for Android applications using dependency context and source-supported functional evidence.</strong></p>

<h2>Overview</h2>
<p>
SIFT is a modular framework for Android library recommendation that combines observed dependency context with description-derived functional evidence through a shared ranking architecture. The framework evaluates three alternative representation stages that use the same downstream ranking design while differing in how application functionality is represented.
</p>

<h2>Stages in SIFT</h2>
<ul>
  <li><strong>Stage A (Dependency Context)</strong> - Uses only observed library co-usage and dependency-context information.</li>
  <li><strong>Stage B (Raw-Description Semantics)</strong> - Combines dependency context with semantic embeddings of application descriptions.</li>
  <li><strong>Stage C (Source-Supported Functional Signal)</strong> - Extracts capability statements using an LLM, applies consensus filtering and textual-support assessment, and constructs functional representations through support-weighted pooling.</li>
</ul>

<h2>Features</h2>
<ul>
  <li><strong>Three-Stage Representation Design</strong> with a shared scoring and ranking architecture.</li>
  <li><strong>Context-Aware Recommendation</strong> using observed application dependencies.</li>
  <li><strong>Description-Aware Representation</strong> for incorporating application-level semantic information.</li>
  <li><strong>LLM-Based Capability Extraction</strong> with consensus filtering and model-assessed textual support.</li>
  <li><strong>Support-Weighted Functional Aggregation</strong> for constructing structured functional representations.</li>
  <li><strong>Single-Command Pipeline Execution</strong> via <code>main.py</code> (train → test → metrics).</li>
</ul>

<h2>Requirements</h2>
<ul>
  <li>Python 3.9+ (recommended)</li>
  <li>PyTorch (GPU optional, CUDA recommended for faster runs)</li>
  <li>Dependencies from <code>requirements.txt</code></li>
</ul>

<h2>Setup</h2>
<pre><code>pip install -r requirements.txt</code></pre>

<h2>Run</h2>
<p>Run the full pipeline (train → test → metrics) for all folds and all <code>rm</code> values:</p>

<pre><code>python main.py --mode all --folds 0,1,2,3,4 --rms 1,3,5 --device cuda</code></pre>

<h2>Outputs</h2>
<ul>
  <li>Model checkpoints are saved during training.</li>
  <li>Recommendation files are generated during testing.</li>
  <li>Final metric summaries are produced during the metrics step (as configured in the pipeline).</li>
</ul>
