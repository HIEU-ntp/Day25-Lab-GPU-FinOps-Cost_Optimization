# GPU FinOps Lab Report

**Student:** Do Minh Hieu  
**Student ID:** 2A202600362

**Date:** 2026-05-13

---

## 1. Giới thiệu

### Mục tiêu của bài lab
Bài lab GPU FinOps giúp sinh viên hiểu và thực hành các kỹ năng quản lý chi phí GPU cloud thông qua:
- Giám sát cluster GPU
- Theo dõi chi phí workload
- Quản lý Spot Instances
- Autoscaling với KEDA-like
- Phân tích và tối ưu chi phí

### Tổng quan về GPU FinOps
FinOps (Financial Operations) là phương pháp quản lý chi phí cloud, giúp tối ưu hóa chi phí GPU trong các ứng dụng AI/ML.

---

## 2. Phân tích từng phần

### Part 1: GPU Cluster Monitoring
- **Kết quả:** Cluster có 3 GPU nodes với các GPU型号 T4, P100, V100
- **Insights:** Metrics cho thấy utilization, memory, temperature được giám sát real-time

### Part 2: Workload Submission & Cost Tracking
- **Kết quả:** Đã submit 5 workloads với various GPU requirements
- **Billing:** Total cost được tính toán dựa trên On-Demand pricing
- **Observations:** Cost tracking giúp identify expensive workloads

### Part 3: Spot Instance Management
- **Spot Pricing:** So sánh giá On-Demand vs Spot
- **Savings:** Preemption simulation cho thấy có thể tiết kiệm đến 70% với Spot instances

### Part 4: Autoscaling (KEDA-like)
- **Policy:** Đã configure scaling rules dựa trên GPU utilization
- **Evaluation:** 5 cycles evaluation cho thấy autoscaler hoạt động đúng logic

### Part 5: Cost Analysis & Optimization
- **Waste Analysis:** Identify resources đang không được sử dụng hiệu quả
- **Recommendations:** Các suggest như right-sizing, spot usage, schedule scaling
- **Dashboard:** Tổng hợp cost metrics và waste percentage

### Part 6: Visualization
- Cost breakdown chart cho thấy phân bổ chi phí theo namespace
- Time-series chart cho thấy xu hướng chi phí theo thời gian

### Part 7: Complete FinOps Workflow
- Full workflow kết hợp tất cả các bước từ monitoring đến optimization

### Part 8: Real GPU Workload (Kaggle/Colab)
- **FP32 vs AMP Comparison:**
  - AMP (Automatic Mixed Precision) giảm memory usage ~50%
  - Training time giảm ~30% với same accuracy
- **Cost Savings:** Tiết kiệm đáng kể khi sử dụng mixed precision

### Part 8.5: Advanced GPU Cost Optimization
- **Multi-GPU Scaling:** Phân tích efficiency khi scale across multiple GPUs
- **Cost Forecasting:** Project future costs với confidence intervals
- **Optimization Strategy:** Prioritized recommendations dựa trên impact

---

## 3. Kết luận và học hỏi

### Kỹ năng FinOps đã học
1. GPU cluster monitoring và metrics collection
2. Cost tracking và billing analysis
3. Spot instance management và savings calculation
4. Autoscaling policy configuration
5. Waste analysis và optimization recommendations

### Các chiến lược cost optimization hiệu quả
1. **Sử dụng Spot Instances:** Tiết kiệm 60-70% cho interruptible workloads
2. **Mixed Precision Training (AMP):** Giảm memory và training time
3. **Right-sizing:** Đúng size GPU theo workload requirements
4. **Autoscaling:** Scale down during low utilization periods

### Ứng dụng thực tế
- Apply vào ML training pipelines để optimize cloud costs
- Monitor GPU usage trong production environments
- Implement spot instance strategy cho batch processing jobs

---

## 4. Technical Details

### Environment
- Docker services running locally
- Cloudflare tunnel for Kaggle/Colab connectivity
- GPU: T4 x2 on Kaggle

### Architecture
- Gateway API: http://localhost:8000
- 6 microservices: GPU Node Manager, Billing API, Spot Manager, Autoscaler, Cost Tracker

---

## 5. Screenshots Summary

| Part | Description | Status |
|------|-------------|--------|
| Part 1 | Cluster Monitoring | ✅ |
| Part 2 | Workload & Billing | ✅ |
| Part 3 | Spot Instances | ✅ |
| Part 4 | Autoscaling | ✅ |
| Part 5 | Cost Analysis | ✅ |
| Part 6 | Visualization | ✅ |
| Part 7 | Full Workflow | ✅ |
| Part 8 | Real GPU Training | ✅ |
| Part 8.5 | Advanced Analysis | ✅ |

---

**Total Screenshots:** 31  
**All Parts Completed:** Yes