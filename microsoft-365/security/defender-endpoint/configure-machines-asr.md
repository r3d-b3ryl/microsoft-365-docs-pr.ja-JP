---
title: ASR ルールの展開と検出を最適化する
description: 攻撃表面の縮小 (ASR) ルールを最適化して、一般的なマルウェアの悪用を特定して防止します。
keywords: オンボード、Intune 管理、Microsoft Defender for Endpoint、Microsoft Defender、Windows Defender、攻撃表面の縮小、ASR、セキュリティ ベースライン
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d2bf9a6fa1f874e7d550d0d0f7a42742a07665eb
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468261"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>ASR ルールの展開と検出を最適化する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[攻撃表面の縮小 (ASR) ルールは、一](./attack-surface-reduction.md) 般的なマルウェアの悪用を特定して防止します。 悪意のあるコードを実行できる可能性のある時間と方法を制御します。 たとえば、JavaScript または VBScript がダウンロードした実行可能ファイルを起動したり、Office マクロからの Win32 API 呼び出しをブロックしたり、USB ドライブから実行されるプロセスをブロックしたりすることができます。


:::image type="content" source="../../media/attack-surface-mgmt.png" alt-text="攻撃表面管理カード" lightbox="../../media/attack-surface-mgmt.png":::
<br>
*攻撃表面管理カード*

攻撃 *表面管理カードは*、次の方法で使用できる Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ツール</a>のエントリ ポイントです。

* ASR ルールが現在組織に展開されている方法について説明します。
* ASR 検出を確認し、誤った検出の可能性を特定します。
* 除外の影響を分析し、除外するファイル パスの一覧を生成します。

[ **Go to attack surface management Reports** \> **Attack** \> **surface reduction rules Add** \> **exclusions] を選択します**。 そこから、ポータルの他のセクションMicrosoft 365 Defenderできます。

:::image type="content" source="images/secconmgmt_asr_m365exlusions.png" alt-text="サイト ポータルの [攻撃表面縮小ルール] ページの [除外] タブをMicrosoft 365 Defenderする" lightbox="images/secconmgmt_asr_m365exlusions.png":::<br>
ポータル ***の [攻撃表面縮小** ルール] ページの [除外のMicrosoft 365 Defender]*

> [!NOTE]
> ポータルにMicrosoft 365 Defenderするには、Microsoft 365 E3または E5 ライセンスと、ユーザーに対して特定の役割を持つアカウントがAzure Active Directory。 [必要なライセンスとアクセス許可についてお読みください](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。

ASR ルールの展開の詳細については、「<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"></a>Microsoft 365 Defender ASR ルールの展開と検出の監視と[管理」を参照してください](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)。

**関連トピック**

* [デバイスが正しく構成されていることを確認する](configure-machines.md)
* [Microsoft Defender for Endpoint にオンボードされているデバイスを取得する](configure-machines-onboarding.md)
* [Microsoft Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを監視する](configure-machines-security-baseline.md)
