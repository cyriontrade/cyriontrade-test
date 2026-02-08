# Fullstack Developer Technical Assessment

## Chart Integration Task

### Overview

Technical assessment for senior fullstack developers. Replace the existing Chart.js implementation with TradingView Lightweight Charts and implement advanced interactive features.

**Time Estimate:** 4-6 hours

---

## Objective

Migrate from Chart.js to TradingView Lightweight Charts and add interactive charting features that demonstrate senior-level expertise.

### Important Notes

**API Requirements:**
- The project uses CoinGecko API for cryptocurrency data
- Free API key recommended (optional for development)
- Understand free tier limitations: 10-50 calls/minute
- Design your solution within these rate limits
- Consider caching strategies to minimize API calls

**Getting Started:**
1. Review existing API implementation in `client/src/services/api.js`
2. Check current data format from `/api/crypto/chart/:id`
3. Understand CoinGecko API constraints before designing features
4. Plan your architecture around API limitations

---

## Requirements

### 1. Chart Library Integration

Replace Chart.js with TradingView Lightweight Charts and implement multiple chart visualization types.

### 2. Interactive Features

Add interactive capabilities including tooltips, zoom, pan, and technical indicators.

### 3. User Interface

Build an intuitive control panel with chart controls, fullscreen mode, and export functionality.

### 4. Performance and Optimization

Ensure smooth performance with efficient data handling and proper state management using custom hooks.

### 5. Responsive Design and Accessibility

Ensure functionality across all devices with proper keyboard navigation and screen reader support.

---

## Deliverables

- Updated chart implementation
- Custom hooks
- Brief documentation (300-500 words)
- Screenshots and demo video

---

## Evaluation

**Architecture and Code Quality (30%)**
- Clean, maintainable code
- Proper component structure
- Reusable hooks
- Good React patterns

**Feature Implementation (30%)**
- All features working
- Smooth interactions
- No critical bugs
- Edge cases handled

**Performance (20%)**
- Smooth animations
- Efficient rendering
- Optimized code
- Small bundle impact

**User Experience (10%)**
- Intuitive controls
- Responsive design
- Visual polish

**Error Handling (10%)**
- Robust error handling
- Clear messages
- Recovery mechanisms

---

## Submission

Create branch `feature/tradingview-chart` and submit a pull request with implementation summary, screenshots, and documentation.

---

## Resources

- [TradingView Lightweight Charts](https://tradingview.github.io/lightweight-charts/)
- Existing codebase for reference

---

## Timeline Guidance

- Hours 1-2: Setup and basic implementation
- Hours 2-4: Features and interactions
- Hours 4-5: Polish and optimization
- Hours 5-6: Documentation and testing

---

## Success Criteria

Deliver a production-quality chart implementation that demonstrates senior-level skills in architecture, performance optimization, and user experience design.

---

**Version:** 2.0  
**Last Updated:** February 2026
