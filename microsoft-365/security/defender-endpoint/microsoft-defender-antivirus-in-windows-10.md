---
title: 次世代の保護
description: 組み込みのマルウェア対策とウイルス対策の保護機能である Microsoft Defender ウイルス対策を管理、構成、使用する方法について説明します。
keywords: Microsoft Defender ウイルス対策, windows defender, マルウェア対策, scep, システム センター エンドポイント保護, システム センター構成マネージャー, ウイルス, マルウェア, 脅威, 検出, 保護, セキュリティ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: cd7fe43fafc587c21fb28b53e0084ccb8c3e5c17
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925997"
---
# <a name="next-generation-protection"></a>次世代の保護

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a>Microsoft Defender ウイルス対策: 次世代の保護

Microsoft Defender ウイルス対策は、Microsoft Defender for Endpoint の次世代保護コンポーネントです。 この保護は、機械学習、ビッグデータ分析、脅威耐性に関する詳細な調査、Microsoft のクラウド インフラストラクチャを組み合わせて、企業組織内のデバイスを保護します。 次世代の保護サービスには以下の機能が含まれています。

- [挙動ベースおよびヒューリスティックのリアルタイム ウイルス対策保護](configure-protection-features-microsoft-defender-antivirus.md)。これには、ファイルとプロセスの動作監視およびその他のヒューリスティックを使用した常時オンのスキャンが含まれています (「*リアルタイム保護*」とも呼ばれています)。 安全ではないと見なされているもののマルウェアとして検出されない可能性のあるアプリの検出とブロックも含まれています。
- [クラウドによる保護](cloud-protection-microsoft-defender-antivirus.md)。これには、新たに出現する脅威のほぼ瞬時の検出とブロックが含まれています。
- [専用の保護および製品の更新プログラム](manage-updates-baselines-microsoft-defender-antivirus.md)。これには、Microsoft Defender ウイルス対策を最新状態に維持することに関連する更新プログラムが含まれています。

## <a name="try-a-demo"></a>デモを試す

[Microsoft Defender for Endpoint のデモ用 Web サイト](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)にアクセスし、以下の保護機能が動作していることを確認したり、デモのシナリオを使用して検証したりしましょう。
- クラウドによる保護
- 事前ブロック (BAFS) 保護
- 望ましくない可能性のあるアプリケーション (PUA) 保護

## <a name="minimum-system-requirements"></a>最小システム要件

Microsoft Defender ウイルス対策のハードウェア要件は、Windows 10 と同じです。 詳細については、以下のリソースを参照してください。

- [ハードウェアの最小要件](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [ハードウェア コンポーネントのガイドライン](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a>次世代の保護サービスを構成する

次世代の保護サービスを構成する方法の詳細については、「[Microsoft Defender ウイルス対策機能を構成する](configure-microsoft-defender-antivirus-features.md)」を参照してください。

> [!Note]  
> Microsoft Defender ウイルス対策の実行中、構成と管理は Windows Server 2016 と Windows Server 2019 でほぼ同じです。ただし、いくつかの違いがあります。 詳細については、「[Windows Server 2016 および 2019 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [Windows Server 2016 および 2019 上の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender ウイルス対策の管理および構成](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策を評価する](evaluate-microsoft-defender-antivirus.md)
