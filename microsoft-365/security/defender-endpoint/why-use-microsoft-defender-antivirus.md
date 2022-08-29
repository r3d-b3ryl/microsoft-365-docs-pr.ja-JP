---
title: Microsoft Defender ウイルス対策をMicrosoft Defender for Endpointと共に使用する必要がある理由
description: 最適な結果を得るには、他の Microsoft オファリングと共に Microsoft Defender ウイルス対策を使用します。
keywords: Windows Defender、ウイルス対策、サード パーティ AV
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 61a70535cc875d75432fb63730cccdb821bfdb99
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67330391"
---
# <a name="better-together-microsoft-defender-antivirus-and-microsoft-defender-for-endpoint"></a>ベストな組み合わせ: Microsoft Defender Antivirus および Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

Microsoft Defender ウイルス対策は、[Microsoft Defender for Endpoint (Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)) の次世代保護コンポーネントです。

Microsoft Defender for Endpointで Microsoft 以外のウイルス対策ソリューションを使用できますが、Defender for Endpoint と共に Microsoft Defender ウイルス対策を使用する利点があります。 Microsoft Defender ウイルス対策は、優れた次世代ウイルス対策ソリューションであるだけでなく、 [エンドポイントの検出や応答](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) 、 [自動調査や修復](/microsoft-365/security/defender-endpoint/automated-investigations)などの他の Defender for Endpoint 機能と組み合わせることで、製品やサービス間で調整される保護を強化できます。

## <a name="11-reasons-to-use-microsoft-defender-antivirus-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender ウイルス対策をMicrosoft Defender for Endpointと共に使用する 11 の理由

|#|メリット|共同作業の重要性|
|--|--|--|
|1|ウイルス対策信号の共有|Microsoft アプリケーションとサービスは、企業組織全体でシグナルを共有し、より強力な単一プラットフォームを提供します。 [MITRE ATT の分析情報&CK ベースのMicrosoft Defender for Endpointの評価に関](https://www.microsoft.com/security/blog/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)するページを参照してください。|
|2|脅威分析とデバイスのスコア|Microsoft Defender ウイルス対策は、 [脅威分析](/microsoft-365/security/defender-endpoint/threat-analytics) と [Microsoft Secure Score for Devices](/microsoft-365/security/defender-endpoint/tvm-microsoft-secure-score-devices) によって使用される基になるシステム データを収集します。 これにより、組織のセキュリティ 体制を改善するための推奨事項や機会など、組織のセキュリティ チームにより意味のある情報が提供されます。|
|3|パフォーマンス|Microsoft Defender for Endpointは Microsoft Defender ウイルス対策を使用するように設計されているため、これらのオファリングを一緒に使用するとパフォーマンスが向上します。 [Microsoft Defender ウイルス対策](evaluate-microsoft-defender-antivirus.md)と[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/evaluate-mde)を評価します。|
|4|ブロックされたマルウェアの詳細|ブロックされたマルウェアの詳細とアクションは、Microsoft Defender ウイルス対策とMicrosoft Defender for Endpointで入手できます。 [マルウェア&他の脅威について理解する](/windows/security/threat-protection/intelligence/understanding-malware)。|
|5|ネットワーク保護|組織のセキュリティ チームは、特定の URL と IP アドレスをブロックすることで、ネットワークを保護できます。 [ネットワークを保護します](/microsoft-365/security/defender-endpoint/network-protection)。|
|6|ファイルのブロック|組織のセキュリティ チームは、特定のファイルをブロックできます。 [ネットワーク内のファイルを停止して検疫します](/microsoft-365/security/defender-endpoint/respond-file-alerts#stop-and-quarantine-files-in-your-network)。|
|7 |攻撃面の縮小|組織のセキュリティ チームは、脆弱性 (攻撃面) を減らし、攻撃者が攻撃を実行する方法を減らすことができます。 攻撃面の削減では、さまざまなルールにクラウド保護が使用されます。 [攻撃面の縮小の概要を確認します](/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction)。|
|8 |イベントの監査|監査イベント信号は、 [エンドポイントの検出機能と応答機能](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)で使用できます。 (これらのシグナルは、Microsoft 以外のウイルス対策ソリューションでは使用できません。|
|9 |地理データ|ISO 270001およびデータ保持に準拠し、組織が選択した地理的主権に従って地理的データが提供されます。 [コンプライアンスオファリング: ISO/IEC 27001:2013 Information Security Management Standards を参照](/microsoft-365/compliance/offering-iso-27001)してください。|
|10|OneDrive を使用したファイルの回復|Microsoft Defender ウイルス対策を[Office 365](/Office365/Enterprise)と共に使用していて、デバイスがランサムウェアによって攻撃されている場合、ファイルは保護され、回復可能です。 [OneDrive Files の復元とWindows Defenderランサムウェア保護をさらに一歩進めます](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-Restore-and-Windows-Defender-takes-ransomware/ba-p/188001)。|
|11|テクニカル サポート|Microsoft Defender ウイルス対策と共にMicrosoft Defender for Endpointを使用することで、テクニカル サポートを呼び出す会社が 1 つ作成されます。 Microsoft Defender ウイルス対策を[使用して、サービスの問題をトラブルシューティング](/microsoft-365/security/defender-endpoint/troubleshoot-mdatp)[し、イベント ログとエラー コードを確認](troubleshoot-microsoft-defender-antivirus.md)します。|

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="learn-more"></a>さらに詳しくは

[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

[Microsoft Defender 脆弱性の管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
