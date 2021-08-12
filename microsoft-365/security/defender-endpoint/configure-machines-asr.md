---
title: ASR ルールの展開と検出を最適化する
description: 攻撃表面の縮小 (ASR) ルールを最適化して、一般的なマルウェアの悪用を特定して防止します。
keywords: オンボード、Intune 管理、Microsoft Defender for Endpoint、Microsoft Defender、Windows Defender、攻撃表面の縮小、ASR、セキュリティ ベースライン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6beda991a4d659b4b6d420b8d069893b363f081b
ms.sourcegitcommit: 346c1332e1e9eebb5c90d6b8553dd70fcabf530a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53567818"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>ASR ルールの展開と検出を最適化する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。

[攻撃表面の縮小 (ASR) ルールは、一](./attack-surface-reduction.md) 般的なマルウェアの悪用を特定して防止します。 悪意のあるコードを実行できる可能性のある時間と方法を制御します。 たとえば、JavaScript または VBScript がダウンロードした実行可能ファイルを起動したり、Office マクロからの Win32 API 呼び出しをブロックしたり、USB ドライブから実行されるプロセスをブロックしたりすることができます。


:::image type="content" source="../../media/attack-surface-mgmt.png" alt-text="攻撃表面管理カード":::
<br>
*攻撃表面管理カード*

攻撃 *表面管理カードは*、セキュリティ センターのツールMicrosoft 365ポイントで、次の場合に使用できます。

* ASR ルールが現在組織に展開されている方法について説明します。
* ASR 検出を確認し、誤った検出の可能性を特定します。
* 除外の影響を分析し、除外するファイル パスの一覧を生成します。

[Go **to attack surface management Reports**  >  **Attack** surface reduction  >  **rules Add**  >  **exclusions] を選択します**。 そこから、セキュリティ センターの他のセクションMicrosoft 365移動できます。

![セキュリティ センターの [攻撃表面の縮小ルール] ページの [除外Microsoft 365追加する](images/secconmgmt_asr_m365exlusions.png)<br>
セキュリティ ***センターの [** 攻撃表面縮小ルール] ページの [除外のMicrosoft 365]*

> [!NOTE]
> セキュリティ センター Microsoft 365アクセスするには、Microsoft 365 E3または E5 ライセンスと、ユーザーに対して特定の役割を持つアカウントAzure Active Directory。 [必要なライセンスとアクセス許可についてお読みください](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。

セキュリティ センターでの ASR ルールの展開のMicrosoft 365、ASR ルールの展開と検出の監視と[管理を参照してください](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)。

**関連トピック**

* [デバイスが正しく構成されていることを確認する](configure-machines.md)
* [Microsoft Defender for Endpoint にオンボードされているデバイスを取得する](configure-machines-onboarding.md)
* [Microsoft Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを監視する](configure-machines-security-baseline.md)
