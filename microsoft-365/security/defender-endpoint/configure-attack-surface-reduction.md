---
title: 攻撃面の減少機能を構成する
description: 攻撃Microsoft Intune、Microsoft Endpoint Configuration Manager、PowerShell コマンドレット、およびグループ ポリシーを使用して、攻撃表面の縮小を構成します。
keywords: asr, 攻撃表面の縮小, Windows Defender, microsoft Defender, ウイルス対策, av
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: jweston-1
ms.author: v-jweston
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 10/14/2021
ms.openlocfilehash: ddd7484adce576a07b18978f20b95df911fa080a
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167540"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>攻撃面の減少機能を構成する

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

Defender for Endpoint には、攻撃表面の縮小機能がいくつか含まれています。 詳細については、「攻撃表面 [の縮小機能の概要」を参照してください](overview-attack-surface-reduction.md)。 環境で攻撃表面の縮小を構成するには、次の手順を実行します。

1. [ハードウェア ベースの分離を有効にMicrosoft Edge。](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)

2. アプリケーション制御を有効にする。

   1. [基本ポリシー] を [Windows] で確認します。 「 [基本ポリシーの例」を参照してください](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)。
   2. 「アプリケーションコントロール[Windows Defenderガイド」を参照してください](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)。
   3. 「アプリケーション[制御 (WDAC) Windows Defenderの展開」を参照してください](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)。

3. [フォルダー アクセスの制御を有効にする](enable-controlled-folders.md)。

4. [[ネットワーク保護] をオンにする](enable-network-protection.md)。

5. [エクスプロイト保護を有効にする](enable-exploit-protection.md)。

6. [攻撃表面の縮小ルールを構成します](enable-attack-surface-reduction.md)。

7. ネットワーク ファイアウォールを設定します。

   1. 高度なセキュリティを備Windows Defender[ファイアウォールの概要を確認します](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。
   2. ファイアウォール ポリシー[をWindows Defenderする](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)方法を決定するには、「ファイアウォール設計ガイド」を使用します。
   3. 高度な[セキュリティWindows Defender組織](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)のファイアウォールをセットアップするには、「ファイアウォールの展開ガイド」を使用します。

> [!TIP]
> ほとんどの場合、攻撃表面の縮小機能を構成する場合、次の方法から選択できます。
>
> - Microsoft エンドポイント マネージャー (現在は、Microsoft IntuneとMicrosoft Endpoint Configuration Manager)
> - グループ ポリシー
> - PowerShell コマンドレット
