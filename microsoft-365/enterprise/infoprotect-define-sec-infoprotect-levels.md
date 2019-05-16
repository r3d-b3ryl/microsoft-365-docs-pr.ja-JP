---
title: '手順 1: セキュリティおよび情報保護のレベルを定義する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 組織のセキュリティおよび情報保護のレベルについて理解し、構成します。
ms.openlocfilehash: 37ef1433f2c117e17c78d297a920424d8e83cbb8
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071977"
---
# <a name="step-1-define-security-and-information-protection-levels"></a>手順 1: セキュリティおよび情報保護のレベルを定義する

*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

この手順では、組織のセキュリティと保護のレベルを定義します。 たとえば、営業部門には必要なセキュリティ レベルは低い可能性があります。 一方で研究部門とその貴重な知的財産には、ファイルを暗号化し研究員だけにアクセスを制限する高いセキュリティ レベルが必要かもしれません。

独自のセキュリティ レベルを定義でき、このようなセキュリティ レベルが既に定義されていることがありますが、少なくとも 3 種類の適用可能なセキュリティおよび保護のレベルを使用する計画を策定することをお勧めします。 作業を開始するためのリストを次に示します。 

- **基準:** これは、データの保護と、データにアクセスする ID およびデバイスの最小限の標準です。基準セキュリティ/保護の推奨事項に従うと、多くの組織や部門のニーズに対応した強力な既定の保護を導入できます。
- **機密:** これは、基準レベルよりも高いレベルで保護する必要があるデータのサブセットに対する保護を強化します。Office 365 環境で特定のデータ セットにこの強化された保護を適用できます。機密データにアクセスする ID およびデバイスには、機密セキュリティ レベルを適用することをお勧めします。
- **高度な規制:** これは、機密性が高いごくわずかなデータ (知的財産または企業秘密として扱われるデータ)、または厳しいセキュリティ規制に準拠する必要があるデータを使用する組織のための最高保護レベルです。Microsoft 365 Enterprise には、組織がこのようなセキュリティの厳しい要件に対応できるようにする機能 (ID およびデバイスを対象とする同等の保護機能を含む) があります。

詳細については、[3 つの層による保護](microsoft-365-policies-configurations.md#three-tiers-of-protection)を参照してください。

中間チェックポイントとして、この手順に対応する[終了条件](infoprotect-exit-criteria.md#crit-infoprotect-step1)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)|[環境のデータ分類方法を構成する](infoprotect-configure-classification.md)|
