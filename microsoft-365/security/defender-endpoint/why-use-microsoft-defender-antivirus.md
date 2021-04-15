---
title: Microsoft Defender ウイルス対策と Microsoft Defender for Endpoint を組み合わせて使用する理由
description: 最適な結果を得る場合は、他の Microsoft 製品と共に Microsoft Defender ウイルス対策を使用してください。
keywords: Windows Defender, ウイルス対策, サード パーティ AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 97b9d95638c205dd47453bf6ad09c0d0487f0f8e
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765637"
---
# <a name="better-together-microsoft-defender-antivirus-and-microsoft-defender-for-endpoint"></a>より良い一緒に:Microsoft Defender Antivirus と Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint)

Microsoft Defender Antivirus は [、Microsoft Defender for Endpoint (Microsoft Defender for](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint) Endpoint) の次世代保護コンポーネントです。 

Microsoft Defender for Endpoint では Microsoft 以外のウイルス対策ソリューションを使用することができますが、Defender for Endpoint と共に Microsoft Defender ウイルス対策を使用する利点があります。 Microsoft Defender Antivirus は優れた次世代ウイルス対策ソリューションであるだけでなく、エンドポイントの検出と応答、自動調査と修復[](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)など、他の[](/microsoft-365/security/defender-endpoint/automated-investigations)Defender for Endpoint 機能と組み合わせて、製品やサービス間で調整された保護を強化します。 

## <a name="11-reasons-to-use-microsoft-defender-antivirus-together-with-microsoft-defender-for-endpoint"></a>Microsoft Defender ウイルス対策と Microsoft Defender for Endpoint を組み合わせて使用する 11 の理由

|# |メリット  |重要な理由 |
|--|--|--|
|1|ウイルス対策信号の共有 |Microsoft のアプリケーションとサービスは、企業組織全体で信号を共有し、より強力な単一プラットフォームを提供します。 「MICROSOFT Defender for Endpoint の MITRE ATT&CK ベースの評価からの [分析情報」を参照してください](https://www.microsoft.com/security/blog/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)。 |
|2|デバイスの脅威分析とスコア |Microsoft Defender Antivirus は、脅威分析と[](/microsoft-365/security/defender-endpoint/threat-analytics)Microsoft Secure Score for Devices で使用される基になる[システム データを収集します](/microsoft-365/security/defender-endpoint/tvm-microsoft-secure-score-devices)。 これにより、組織のセキュリティ チームは、組織のセキュリティ体制を改善するための推奨事項や機会など、より有意義な情報を提供します。 |
|3|パフォーマンス |Microsoft Defender for Endpoint は、Microsoft Defender ウイルス対策を使用するように設計されています。そのため、これらのサービスを一緒に使用するとパフォーマンスが向上します。 [エンドポイントの Microsoft Defender ウイルス対策](evaluate-microsoft-defender-antivirus.md)[と Microsoft Defender を評価します](/microsoft-365/security/defender-endpoint/evaluate-mde)。|
|4|ブロックされたマルウェアの詳細 |ブロックされたマルウェアの詳細とアクションは、Microsoft Defender Antivirus および Microsoft Defender for Endpoint で利用できます。 [マルウェアと他&を理解します](/windows/security/threat-protection/intelligence/understanding-malware)。|
|5|ネットワーク保護 |組織のセキュリティ チームは、特定の URL と IP アドレスをブロックしてネットワークを保護できます。 [ネットワークを保護します](/microsoft-365/security/defender-endpoint/network-protection)。|
|6|ファイルのブロック |組織のセキュリティ チームは、特定のファイルをブロックできます。 [ネットワーク内のファイルを停止して検疫します](/microsoft-365/security/defender-endpoint/respond-file-alerts#stop-and-quarantine-files-in-your-network)。|
|7|攻撃表面の縮小 |組織のセキュリティ チームは、脆弱性 (攻撃表面) を軽減し、攻撃者が攻撃を実行する方法を少なくすることができます。 攻撃表面の縮小では、複数のルールに対してクラウド保護が使用されます。 [攻撃表面の縮小の概要を確認します](/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction)。|
|8|監査イベント |監査イベント信号は、エンドポイント検出および応答 [機能で使用できます](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)。 (これらの信号は、Microsoft 以外のウイルス対策ソリューションでは使用できません)。 |
|9|地理データ |ISO 270001 およびデータ保持に準拠した地理的データは、組織で選択された地理的主権に従って提供されます。 「 [コンプライアンス製品: ISO/IEC 27001:2013 Information Security Management Standards」を参照してください](/microsoft-365/compliance/offering-iso-27001)。 |
|10|OneDrive によるファイルの回復 |Microsoft Defender Antivirus を Office [365](/Office365/Enterprise)と共に使用している場合、デバイスがランサムウェアによって攻撃された場合、ファイルは保護および回復可能になります。 [OneDrive Files Restore and Windows Defenderランサムウェア保護をさらに一歩進めます](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-Restore-and-Windows-Defender-takes-ransomware/ba-p/188001)。|
|11|テクニカル サポート |Microsoft Defender for Endpoint と Microsoft Defender ウイルス対策を組み合わせて使用すると、1 つの会社でテクニカル サポートを呼び出す必要があります。 Microsoft Defender Antivirus[を使用して、](/microsoft-365/security/defender-endpoint/troubleshoot-mde)[サービスの問題をトラブルシューティングし、イベント ログとエラー コードを確認します](troubleshoot-microsoft-defender-antivirus.md)。 |


## <a name="learn-more"></a>詳細情報

[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)

[脅威&の管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)