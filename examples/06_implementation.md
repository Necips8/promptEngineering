# Phase 3: Implementierung & Testing (coder & tester)

**Rollen:** Entwickler & QA-Ingenieur

## 1. Implementierung: Punkt-Logik (coder.systemPrompt)

Hier ist die Kernfunktion zur Berechnung der Punkte basierend auf der Müllkategorie, implementiert in TypeScript.

```typescript
/**
 * Berechnet die GreenPoints basierend auf der Müllkategorie und dem Gewicht.
 * 
 * @param category - Die Kategorie des Abfalls (z.B. 'plastic', 'glass', 'paper')
 * @param weightGrams - Optionales Gewicht in Gramm (Standard: 100g für kleine Teile)
 * @returns Anzahl der vergebenen Punkte
 */
export function calculateGreenPoints(category: string, weightGrams: number = 100): number {
  const basePoints: Record<string, number> = {
    'plastic': 10,
    'glass': 15,
    'paper': 5,
    'metal': 20,
    'bio': 2
  };

  const pointsPerItem = basePoints[category.toLowerCase()] || 0;
  
  // Bonus für größere Mengen (Skalierungsfaktor)
  const weightMultiplier = Math.max(1, Math.floor(weightGrams / 500));
  
  return pointsPerItem * weightMultiplier;
}
```

## 2. Testfälle (tester.systemPrompt)

Ich habe folgende Test-Suite (Jest) erstellt, um die Logik abzusichern:

```typescript
import { calculateGreenPoints } from './points';

describe('calculateGreenPoints', () => {
  test('should return 10 points for plastic', () => {
    expect(calculateGreenPoints('plastic')).toBe(10);
  });

  test('should handle case-insensitivity', () => {
    expect(calculateGreenPoints('GLASS')).toBe(15);
  });

  test('should return 0 for unknown categories', () => {
    expect(calculateGreenPoints('pizza-box')).toBe(0);
  });

  test('should scale points with weight (multiplier)', () => {
    // 1100g Plastic -> 10 points * 2 (multiplier for >1000g) = 20 points
    expect(calculateGreenPoints('plastic', 1100)).toBe(20);
  });

  test('should return minimum points for low weight', () => {
    expect(calculateGreenPoints('metal', 10)).toBe(20);
  });
});
```

**QA-Anmerkung:** Wir müssen noch sicherstellen, dass die `weightGrams` nicht negativ sein können. Hier sollte die Implementierung eine Fehlermeldung werfen.
