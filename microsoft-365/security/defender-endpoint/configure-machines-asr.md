---
title: ASR ルールの展開と検出を最適化する
description: 攻撃表面の縮小 (ASR) ルールを最適化して、一般的なマルウェアの悪用を特定して防止します。
keywords: オンボード、Intune 管理、MDATP、WDATP、Microsoft Defender、Windows Defender、高度な脅威保護、攻撃表面の縮小、ASR、セキュリティ ベースライン
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
ms.openlocfilehash: a5ce39bb3ff0bf3eea4ac4e89c554de43499b15f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165479"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>ASR ルールの展開と検出を最適化する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)。

[攻撃表面の縮小 (ASR) ルールは、一](./attack-surface-reduction.md) 般的なマルウェアの悪用を特定して防止します。 悪意のあるコードを実行できる可能性のある時間と方法を制御します。 たとえば、JavaScript または VBScript がダウンロードした実行可能ファイルを起動したり、Office マクロからの Win32 API 呼び出しをブロックしたり、USB ドライブから実行されるプロセスをブロックしたりすることができます。

![攻撃表面管理カード](images/secconmgmt_asr_card.png)<br>
*攻撃表面管理カード*

攻撃 *表面管理カードは* 、Microsoft 365 セキュリティ センターのツールのエントリ ポイントで、次の使用が可能です。

* ASR ルールが現在組織に展開されている方法について説明します。
* ASR 検出を確認し、誤った検出の可能性を特定します。
* 除外の影響を分析し、除外するファイル パスの一覧を生成します。

[Go **to attack surface management**  >  **Monitoring] &レポート>[除外の>追加] を選択します**。 そこから、Microsoft 365 セキュリティ センターの他のセクションに移動できます。

![Microsoft 365 セキュリティ センターの [攻撃表面の縮小ルール] ページの [除外] タブを追加する](images/secconmgmt_asr_m365exlusions.png)<br>
Microsoft 365 セキュリティ センターの [攻撃表面縮小ルール] ページの [*除外の追加] タブ*

> [!NOTE]
> Microsoft 365 セキュリティ センターにアクセスするには、Microsoft 365 E3 または E5 ライセンスと、Azure Active Directory で特定の役割を持つアカウントが必要です。 [必要なライセンスとアクセス許可についてお読みください](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)。

Microsoft 365 セキュリティ センターでの ASR ルールの展開の詳細については [、「ASR](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)ルールの展開と検出の監視と管理」を参照してください。

**関連トピック**

* [デバイスが正しく構成されていることを確認する](configure-machines.md)
* [Microsoft Defender for Endpoint にオンボードされているデバイスを取得する](configure-machines-onboarding.md)
* [Microsoft Defender for Endpoint セキュリティ ベースラインへのコンプライアンスを監視する](configure-machines-security-baseline.md)
