---
title: 攻撃表面の縮小機能を構成する
description: 攻撃Microsoft Intune、Microsoft Endpoint Configuration Manager、PowerShell コマンドレット、およびグループ ポリシーを使用して、攻撃表面の縮小を構成します。
keywords: asr, 攻撃表面の縮小, Windows Defender, microsoft Defender, ウイルス対策, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: d2f984e21338e2f9a4ed579cde2d74339031d649
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770963"
---
# <a name="configure-attack-surface-reduction-capabilities"></a>攻撃表面の縮小機能を構成する

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)。

Defender for Endpoint には、攻撃表面の縮小機能がいくつか含まれています。 詳細については、「攻撃表面 [の縮小機能の概要」を参照してください](overview-attack-surface-reduction.md)。 環境で攻撃表面の縮小を構成するには、次の手順を実行します。 

1. [ハードウェア ベースの分離を有効にMicrosoft Edge。](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)

2. アプリケーション制御を有効にする。 

   1. [基本ポリシー] を [Windows] で確認します。 基本 [ポリシーの例を参照してください](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)。
   2. アプリケーション コントロール [の設計ガイドを参照してください](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)。
   3. アプリケーション コントロールの [設計ガイドを参照してください](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)。

3. [フォルダー アクセスの制御を有効にする](enable-controlled-folders.md)。

4. [[ネットワーク保護] をオンにする](enable-network-protection.md)。

5. [エクスプロイト保護を有効にする](enable-exploit-protection.md)。

6. [攻撃表面の縮小ルールを構成します](enable-attack-surface-reduction.md)。

7. ネットワーク ファイアウォールを設定します。

   1. 高度なセキュリティを備Windows Defender ファイアウォール[の概要を確認します](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。
   2. ファイアウォール ポリシー [Windows Defender ファイアウォールする方法](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide)を決定するには、次の設計ガイドを使用します。
   3. 高度な[セキュリティWindows Defender ファイアウォール組織](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)のファイアウォールをセットアップするには、次の展開ガイドを使用します。 

> [!TIP]
> ほとんどの場合、攻撃表面の縮小機能を構成する場合、次の方法から選択できます。
> - Microsoft エンドポイント マネージャー (現在は、Microsoft IntuneとMicrosoft Endpoint Configuration Manager)
> - グループ ポリシー
> - PowerShell コマンドレット
