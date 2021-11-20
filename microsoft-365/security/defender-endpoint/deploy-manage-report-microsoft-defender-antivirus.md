---
title: アプリの展開、管理、レポートMicrosoft Defender ウイルス対策
description: Intune、グループ ポリシー、powerShell、または WMI Microsoft Defender ウイルス対策を使用Microsoft Endpoint Configuration Manager展開および管理できます。
keywords: 展開、管理、更新、保護、Microsoft Defender ウイルス対策
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: f1ecba248046755a9258ffd94da66859a26a0c6d
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61122239"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>アプリの展開、管理、レポートMicrosoft Defender ウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

さまざまな方法で、Microsoft Defender ウイルス対策を展開、管理、およびレポートできます。

Microsoft Defender ウイルス対策 クライアントは Windows 10 および Windows 11 のコアパーツとしてインストールされているので、エンドポイントへのクライアントの従来の展開は適用されません。

ただし、ほとんどの場合、Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Defender for Cloud、またはグループ ポリシー オブジェクトを使用してエンドポイントで保護サービスを有効にする必要があります。これは次の表で説明します。

次の追加リンクも表示されます。

- 製品とMicrosoft Defender ウイルス対策更新プログラムの管理を含む、保護の管理
- 保護に関するMicrosoft Defender ウイルス対策レポート

> [!IMPORTANT]
> ほとんどの場合、Windows 10または Windows 11 は、Microsoft Defender ウイルス対策 が実行され、最新の状態にある別のウイルス対策製品を検出した場合に無効になります。 サードパーティのウイルス対策製品が機能する前に、Microsoft Defender ウイルス対策アンインストールする必要があります。 サード パーティ製のウイルス対策製品を再び有効またはインストールすると、Windows 10または Windows 11 が自動的にMicrosoft Defender ウイルス対策。

ツール|展開オプション (<a href="#fn2" id="ref2">2</a>)|管理オプション (ネットワーク全体の構成とポリシーまたはベースラインの展開) ([3](#fn3))|レポート オプション
---|---|---|---
Microsoft Intune|[Intune でエンドポイント保護設定を追加する](/intune/endpoint-protection-configure)|[Intune でデバイス制限設定を構成する](/intune/device-restrictions-configure)| [Intune コンソールを使用してデバイスを管理する](/intune/device-management)
Microsoft エンドポイント マネージャー ([1](#fn1))|[Endpoint Protection サイト システムの役割][] を使用し、[カスタム クライアント設定でEndpoint Protectionを有効にする][]|[既定およびカスタマイズされたマルウェア対策ポリシー][] と [クライアント管理][]|既定の [Configuration Manager 監視ワークスペース][] と [電子メール通知][] を使用する
グループ ポリシーと Active Directory (ドメイン参加)|グループ ポリシー オブジェクトを使用して構成の変更を展開し、Microsoft Defender ウイルス対策確認します。|グループ ポリシー オブジェクト (GPO) を使用して [Microsoft Defender ウイルス対策][] および [構成Windows Defender機能][]|エンドポイント レポートは、グループ ポリシーでは使用できません。 [グループ ポリシー] の一覧を生成して、設定またはポリシーが適用されていないかどうかを判断できます][]
PowerShell|グループ ポリシー、グループ ポリシー、Microsoft Endpoint Configuration Manager、または個々のエンドポイントに手動で展開します。|Defender モジュールで使用できる [Set-MpPreference] コマンドレットと [Update-MpSignature] コマンドレットを使用します。|適切な [Defender モジュールで使用可能な Get- コマンドレット][] を使用します。
Windows Management Instrumentation|グループ ポリシー、グループ ポリシー、Microsoft Endpoint Configuration Manager、または個々のエンドポイントに手動で展開します。|[クラスの Set メソッド][MSFT_MpPreference][] と [クラスの Update メソッド][] をMSFT_MpSignatureします。|[MSFT_MpComputerStatus][] クラスと [wmIv2 Provider][] の関連クラスの get メソッドWindows Defender使用します。
Microsoft Azure|Azure ポータルMicrosoft Antimalware仮想マシン構成を使用するか、または仮想マシンVisual Studioコマンドレットを使用して Azure Azure PowerShell[展開します](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios)。 Microsoft [Defender for Cloud* にエンドポイント保護をインストールできます。](/azure/security-center/security-center-install-endpoint-protection)|仮想[Microsoft Antimalwareクラウド サービス](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)のサーバーを構成するか、Azure PowerShellサンプル[を使用する](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|監視[Microsoft Antimalware有効にするには、仮想マシンとクラウド](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)サービスのAzure PowerShellコマンドレットを使用します。 Azure Active Directory の利用状況レポートを確認して、[感染している可能性のあるデバイス][] レポートを含む疑わしいアクティビティを特定し、[Microsoft Defender ウイルス対策 イベント][] を報告する SIEM ツールを構成し、そのツールを AAD のアプリとして追加することもできます。

1. <span id="fn1" />クラウドによる保護に関連する一部の機能と機能の可用性は、Microsoft エンドポイント マネージャー (Current Branch) と System Center Configuration Manager で異なります。 このライブラリでは、11、Windows 10、Windows、Windows Server 2016、Microsoft エンドポイント マネージャー (Current Branch) に焦点を当てました。 主[な違いを説明する表については](cloud-protection-microsoft-defender-antivirus.md)、「Microsoft Defender ウイルス対策で Microsoft クラウド提供の保護を使用する」を参照してください。 [(テーブルに戻る)](#ref2)

2. <span id="fn2" />11 Windows 10および Windowsでは、Microsoft Defender ウイルス対策クライアントまたはサービスをインストールまたは展開せずに使用できるコンポーネントです。 サード パーティ製のウイルス対策製品がアンインストールまたは古い場合に自動的に有効Windows Server 2016。 したがって、従来の展開は必要ありません。 ここでの展開とは、エンドポイントまたはサーバーでMicrosoft Defender ウイルス対策コンポーネントが使用可能で有効になっているか確認する方法を指します。 [(テーブルに戻る)](#ref2)

3. <span id="fn3" />製品と保護の更新プログラムの構成を含む機能と保護の構成については、[この](configure-notifications-microsoft-defender-antivirus.md)ライブラリの「Microsoft Defender ウイルス対策機能の構成」セクションで説明します。 [(テーブルに戻る)](#ref2)

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
---|---
[保護の展開と有効化Microsoft Defender ウイルス対策する](deploy-microsoft-defender-antivirus.md) | クライアントは Windows 10 または Windows 11 のコアパーツとしてインストールされ、従来の展開は適用されませんが、Microsoft Endpoint Configuration Manager、Microsoft Intune、またはグループ ポリシー オブジェクトを使用してエンドポイントでクライアントを有効にする必要があります。
[更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する](manage-updates-baselines-microsoft-defender-antivirus.md) | エンドポイントでのクライアントの更新Microsoft Defender ウイルス対策セキュリティ インテリジェンス (保護更新プログラム) の更新の 2 つの部分があります。 セキュリティ インテリジェンスは、さまざまな方法で、Microsoft Endpoint Configuration Manager、PowerShell、WMI を使用して更新できます。
[保護の監視とMicrosoft Defender ウイルス対策する](report-monitor-microsoft-defender-antivirus.md) | Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Operations Management Suite のコンプライアンス更新アドイン、またはサードパーティの SIEM 製品 (Windows イベント ログを使用) を使用して、保護状態を監視し、エンドポイント保護に関するレポートを作成できます。
