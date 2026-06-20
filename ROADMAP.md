# ROADMAP.md — Computer Vision Project

## 12-Month Vision

Evolve from a reference/documentation repository into a fully deployable, production-grade computer vision toolkit with hardware-optimized inference engines, comprehensive benchmarks, and first-class support for modern transformer-based detection, segmentation, and vision-language models across edge and cloud targets.

---

## Quarterly Milestones

### Q1 (Months 1–3): Foundation & Migration
- [ ] Upgrade Python target to 3.14, OpenCV to v5, CUDA to 13
- [ ] Implement C++26 build system with CMake presets for all 4 hardware targets
- [ ] Create conda environment (`py314`) with pinned dependencies
- [ ] Establish CI/CD pipeline (GitHub Actions) with linting, type checking, and unit tests
- [ ] Benchmark classical CV baselines on all target hardware
- [ ] Migrate SIFT/ORB/HAAR implementations to OpenCV v5 API

### Q2 (Months 4–6): Modern DL Integration
- [ ] Integrate RT-DETR v2 and YOLO11 via Ultralytics with TensorRT backend
- [ ] Implement INT8 quantization pipeline with QDQ calibration for NVIDIA Spark
- [ ] Add SAM 2 integration for image/video segmentation
- [ ] Build Grounding DINO zero-shot detection API
- [ ] Create unified inference engine abstraction (ONNX Runtime, TensorRT, Core ML, OpenVINO)
- [ ] Achieve <10ms latency targets on NVIDIA Spark and Apple M5 Max

### Q3 (Months 7–9): Edge Optimization & 3D Vision
- [ ] Optimize MobileViTv3 and YOLO-NAS for Raspberry Pi 5 (16GB ARM64)
- [ ] Implement Intel Ultra 9 Gen 2 AVX-512 kernel dispatch with hybrid core scheduling
- [ ] Deploy 3D Gaussian Splatting pipeline on Apple M5 Max Unified Memory
- [ ] Build ViTPose++ and RTMPose real-time pose estimation pipeline
- [ ] Create hardware-aware NAS with automatic model selection per device
- [ ] Achieve 60 FPS video segmentation on all non-RPi5 targets

### Q4 (Months 10–12): Vision-Language & Production
- [ ] Integrate multimodal LLM API (GPT-4V / LLaVA-NeXT / InternVL2) with automatic backend selection
- [ ] Build end-to-end pipelines: detection → segmentation → tracking → 3D reconstruction
- [ ] Complete production benchmark suite with automated regression testing
- [ ] Publish comprehensive documentation with hardware-specific deployment guides
- [ ] Open-source release with pre-trained model weights and containerized deployment
- [ ] Performance audit: validate all latency/throughput targets across hardware matrix

---

## Technical Debt

| ID | Item | Priority | Effort |
|----|------|----------|--------|
| TD-1 | Remove legacy OpenCV 4.x API calls (imread flags, drawContours) | High | 2 days |
| TD-2 | Replace `typing.Optional` with `X | None` (Python 3.10+ syntax) | Low | 1 day |
| TD-3 | Consolidate duplicated preprocessing utilities across modules | Medium | 3 days |
| TD-4 | Add type hints to all public APIs (currently ~60% coverage) | High | 4 days |
| TD-5 | Migrate from `setup.py` to `pyproject.toml` | Medium | 1 day |
| TD-6 | Replace deprecated `cv2.findContours` return value unpacking | High | 0.5 days |
| TD-7 | Add C++26 `std::expected` error handling for CUDA kernels | Medium | 5 days |
| TD-8 | Eliminate circular imports between `detection` and `segmentation` modules | Low | 2 days |
| TD-9 | Harden GPU memory management (leak detection in long-running pipelines) | High | 3 days |
| TD-10 | Add comprehensive docstrings to all modules (currently sparse) | Low | 3 days |

---

## Future Features

### Near-Term (6 months)
- Real-time multi-object tracking with Re-ID (BoT-SORT / ByteTrack integration)
- Video instance segmentation with temporal smoothing
- Active learning pipeline for continuous model improvement
- Web-based visualization dashboard for benchmark results
- Docker + Kubernetes deployment manifests for cloud inference

### Mid-Term (12 months)
- Federated learning support for privacy-preserving model training
- Automatic model compression (pruning + quantization) pipeline
- Edge-cloud hybrid inference with adaptive offloading
- Custom CUDA kernel library for vision preprocessing operations
- ROS2 integration for robotics deployment

### Long-Term (18+ months)
- Neural Radiance Fields (NeRF) real-time training on consumer hardware
- Diffusion model integration for synthetic data generation
- Autonomous driving perception stack (multi-camera, LiDAR fusion)
- Vision-language model fine-tuning pipeline for domain-specific tasks
- Hardware-in-the-loop testing framework for production validation
