---
title: アプリの展開、管理、レポートMicrosoft Defender ウイルス対策
description: Intune、グループ ポリシー、powerShell、または WMI Microsoft Defender ウイルス対策を使用Microsoft Endpoint Configuration Manager展開および管理できます。
keywords: 展開、管理、更新、保護、Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: cf5796a7df38601c7af79ec7bd11f124865e31af
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220625"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>アプリの展開、管理、レポートMicrosoft Defender ウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

さまざまな方法で、Microsoft Defender ウイルス対策を展開、管理、およびレポートできます。

クライアントは Microsoft Defender ウイルス対策のコア部分としてインストールWindows 10、エンドポイントへのクライアントの従来の展開は適用されません。

ただし、ほとんどの場合、Microsoft Intune、Microsoft Endpoint Configuration Manager、Azure Defender、またはグループ ポリシー オブジェクトを使用してエンドポイントで保護サービスを有効にする必要があります。これは次の表で説明します。

次の追加リンクも表示されます。

- 製品とMicrosoft Defender ウイルス対策更新プログラムの管理を含む、保護の管理
- 保護に関するMicrosoft Defender ウイルス対策レポート

> [!IMPORTANT]
> ほとんどの場合、実行中Windows 10最新Microsoft Defender ウイルス対策ウイルス対策製品が見Microsoft Defender ウイルス対策場合、ウイルス対策ソフトウェアは無効になります。 サードパーティのウイルス対策製品が機能する前に、Microsoft Defender ウイルス対策アンインストールする必要があります。 サードパーティのウイルス対策製品を再び有効またはインストールする場合は、Windows 10自動的にMicrosoft Defender ウイルス対策。

ツール|展開オプション (<a href="#fn2" id="ref2">2</a>)|管理オプション (ネットワーク全体の構成とポリシーまたはベースラインの展開) ([3](#fn3))|レポート オプション
---|---|---|---
Microsoft Intune|[Intune でエンドポイント保護設定を追加する](/intune/endpoint-protection-configure)|[Intune でデバイス制限設定を構成する](/intune/device-restrictions-configure)| [Intune コンソールを使用してデバイスを管理する](/intune/device-management)
Microsoft エンドポイント マネージャー ([1](#fn1))|ポイント サイト[システムEndpoint Protectionを使用][]し、カスタム[クライアント設定でEndpoint Protectionを有効にする][]|既定[およびカスタマイズされたマルウェア対策ポリシーとクライアント][][管理][]|既定の [Configuration Manager 監視ワークスペースと電子][] メール [通知を使用する][]
グループ ポリシーと Active Directory (ドメイン参加)|グループ ポリシー オブジェクトを使用して構成の変更を展開し、Microsoft Defender ウイルス対策確認します。|グループ ポリシー オブジェクト (GPO) を使用して、グループ ポリシーの更新オプションを構成[Microsoft Defender ウイルス対策][]機能の[構成Windows Defenderします。][]|エンドポイント レポートは、グループ ポリシーでは使用できません。 グループ ポリシーの一覧を生成して、設定またはポリシーが適用されていない [かどうかを判断できます。][]
PowerShell|グループ ポリシー、グループ ポリシー、Microsoft Endpoint Configuration Manager、または個々のエンドポイントに手動で展開します。|Defender モジュール [で使用できる Set-MpPreference] コマンドレットと [Update-MpSignature] コマンドレットを使用します。|Defender モジュールで [使用できる適切な Get- コマンドレットを使用する][]
Windows Management Instrumentation|グループ ポリシー、グループ ポリシー、Microsoft Endpoint Configuration Manager、または個々のエンドポイントに手動で展開します。|クラスの [Set メソッドと MSFT_MpPreference クラス][] の Update [メソッドをMSFT_MpSignatureします。][]|WMIv2[プロバイダー MSFT_MpComputerStatus][]関連付けられているクラスの get メソッドと Windows Defender[を使用します。][]
Microsoft Azure|Azure ポータルMicrosoft Antimalware仮想マシン構成を使用するか、または仮想マシンVisual Studioコマンドレットを使用して Azure Azure PowerShell[展開します](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios)。 Azure [Defender* にエンドポイント保護をインストールできます。](/azure/security-center/security-center-install-endpoint-protection)|仮想[Microsoft Antimalwareクラウド サービス](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)のサーバーを構成するか、Azure PowerShellサンプル[を使用する](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|監視[Microsoft Antimalware有効にするには、仮想マシンとクラウド](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)サービスのAzure PowerShellコマンドレットを使用します。 Azure Active Directory の利用状況レポートを確認して、疑わしいアクティビティ (感染の可能性がある[][]デバイスレポートを含む) を確認し[、Microsoft Defender ウイルス対策][]イベントを報告し、そのツールを AAD のアプリとして追加する SIEM ツールを構成することもできます。

1. <span id="fn1" />クラウドによる保護に関連する一部の機能と機能の可用性は、Microsoft エンドポイント マネージャー (Current Branch) と System Center Configuration Manager で異なります。 このライブラリでは、現在のブランチWindows 10、Windows Server 2016、Microsoft エンドポイント マネージャーに焦点を当てました。 主[な違いを説明する表については](cloud-protection-microsoft-defender-antivirus.md)、「Microsoft Defender ウイルス対策で Microsoft クラウド提供の保護を使用する」を参照してください。 [(テーブルに戻る)](#ref2)

2. <span id="fn2" />このWindows 10、Microsoft Defender ウイルス対策は、追加のクライアントまたはサービスをインストールまたは展開せずに使用できるコンポーネントです。 サード パーティのウイルス対策製品がアンインストールまたは古い場合に自動的に有効[になります](microsoft-defender-antivirus-on-windows-server.md)(ただし、Windows Server 2016)。 したがって、従来の展開は必要ありません。 ここでの展開とは、エンドポイントまたはサーバーでMicrosoft Defender ウイルス対策コンポーネントが使用可能で有効になっているか確認する方法を指します。 [(テーブルに戻る)](#ref2)

3. <span id="fn3" />製品と保護の更新プログラムの構成を含む機能と保護の構成については、[この](configure-notifications-microsoft-defender-antivirus.md)ライブラリの「Microsoft Defender ウイルス対策機能の構成」セクションで説明します。 [(テーブルに戻る)](#ref2)

[Endpoint Protection サイト システムの役割]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[既定のマルウェア対策ポリシーとカスタマイズされたマルウェア対策ポリシー]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[クライアント管理]:  /configmgr/core/clients/manage/manage-clients
[カスタム クライアントEndpoint Protectionを有効にする]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Configuration Manager 監視ワークスペース]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[電子メール通知]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[クラスの set メソッドMSFT_MpPreferenceします。]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[クラスの update メソッドMSFT_MpSignatureします。]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Windows DefenderWMIv2 プロバイダー]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Defender モジュールで使用できる Get- コマンドレット]: /powershell/module/defender/
[ユーザーの更新オプションを構成Microsoft Defender ウイルス対策]: manage-updates-baselines-microsoft-defender-antivirus.md
[機能Windows Defender構成する]: configure-microsoft-defender-antivirus-features.md
[設定またはポリシーが適用されていないかどうかを判断するグループ ポリシー]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[感染している可能性のあるデバイス]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Microsoft Defender ウイルス対策イベント]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
---|---
[保護の展開と有効化Microsoft Defender ウイルス対策する](deploy-microsoft-defender-antivirus.md) | クライアントは Windows 10 のコアパーツとしてインストールされ、従来の展開は適用されませんが、Microsoft Endpoint Configuration Manager、Microsoft Intune、またはグループ ポリシー オブジェクトを使用してエンドポイントでクライアントを有効にする必要があります。
[更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する](manage-updates-baselines-microsoft-defender-antivirus.md) | エンドポイントでのクライアントの更新Microsoft Defender ウイルス対策セキュリティ インテリジェンス (保護更新プログラム) の更新の 2 つの部分があります。 セキュリティ インテリジェンスは、さまざまな方法で、Microsoft Endpoint Configuration Manager、PowerShell、WMI を使用して更新できます。
[保護の監視とMicrosoft Defender ウイルス対策する](report-monitor-microsoft-defender-antivirus.md) | Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Operations Management Suite のコンプライアンス更新アドイン、またはサードパーティの SIEM 製品 (Windows イベント ログを使用) を使用して、保護状態を監視し、エンドポイント保護に関するレポートを作成できます。