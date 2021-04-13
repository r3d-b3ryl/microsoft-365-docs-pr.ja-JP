---
title: Microsoft Defender ウイルス対策の展開、管理、およびレポート
description: Intune、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell、WMI を使用して Microsoft Defender ウイルス対策を展開および管理できます。
keywords: 展開、管理、更新、保護、Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a9cd04300e67f956b50f07c02f3dc00c515f02eb
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691515"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Microsoft Defender ウイルス対策の展開、管理、およびレポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender ウイルス対策の展開、管理、レポートは、さまざまな方法で行うことができます。

Microsoft Defender Antivirus クライアントは Windows 10 のコアパーツとしてインストールされています。そのため、エンドポイントへのクライアントの従来の展開は適用されません。

ただし、ほとんどの場合、次の表に示す Microsoft Intune、Microsoft Endpoint Configuration Manager、Azure Defender、またはグループ ポリシー オブジェクトを使用して、エンドポイントで保護サービスを有効にする必要があります。

次の追加リンクも表示されます。

- 製品および保護更新プログラムの管理を含む、Microsoft Defender ウイルス対策保護の管理
- Microsoft Defender ウイルス対策保護に関するレポート

> [!IMPORTANT]
> ほとんどの場合、Windows 10 は、実行中の最新の別のウイルス対策製品を検出した場合、Microsoft Defender ウイルス対策を無効にします。 Microsoft Defender Antivirus が機能する前に、サードパーティのウイルス対策製品を無効またはアンインストールする必要があります。 サードパーティのウイルス対策製品を再び有効またはインストールすると、Windows 10 は Microsoft Defender ウイルス対策を自動的に無効にします。

ツール|展開オプション (<a href="#fn2" id="ref2">2</a>)|管理オプション (ネットワーク全体の構成とポリシーまたはベースラインの展開) ([3](#fn3))|レポート オプション  
---|---|---|---  
Microsoft Intune|[Intune でエンドポイント保護設定を追加する](/intune/endpoint-protection-configure)|[Intune でデバイス制限設定を構成する](/intune/device-restrictions-configure)| [Intune コンソールを使用してデバイスを管理する](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1))|エンドポイント保護 [ポイント サイト システムの役割を使用し][] 、カスタム [クライアント設定でエンドポイント保護を有効にする][]|既定[およびカスタマイズされたマルウェア対策ポリシーとクライアント][][管理][]|既定の [Configuration Manager 監視ワークスペースと電子][] メール [通知を使用する][]  
グループ ポリシーと Active Directory (ドメイン参加)|グループ ポリシー オブジェクトを使用して構成の変更を展開し、Microsoft Defender ウイルス対策が有効になっているか確認します。|グループ ポリシー オブジェクト (GPO) を使用して [Microsoft Defender ウイルス][] 対策の更新オプションを構成し、グループ ポリシー [Windows Defender構成する][]|エンドポイント レポートは、グループ ポリシーでは使用できません。 グループ ポリシーの一覧を生成して、設定またはポリシーが適用されていない [かどうかを判断できます。][]
PowerShell|グループ ポリシー、Microsoft Endpoint Configuration Manager、または個々のエンドポイントに手動で展開します。|Defender モジュール [で使用できる Set-MpPreference] コマンドレットと [Update-MpSignature] コマンドレットを使用します。|Defender モジュールで [使用できる適切な Get- コマンドレットを使用する][]
Windows Management Instrumentation|グループ ポリシー、Microsoft Endpoint Configuration Manager、または個々のエンドポイントに手動で展開します。|クラスの [Set メソッドと MSFT_MpPreference クラス][] の Update [メソッドをMSFT_MpSignatureします。][]|WMIv2 [プロバイダー MSFT_MpComputerStatus][] 関連付けられているクラスの get メソッドと Windows Defender [を使用します。][]
Microsoft Azure|Microsoft Antimalware for Azure を Azure portal に展開するには、仮想マシンVisual Studioを使用するか [、Azure PowerShell コマンドレットを使用します](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios)。 Azure [Defender* にエンドポイント保護をインストールできます。](/azure/security-center/security-center-install-endpoint-protection)|[Azure PowerShell コマンドレットを使用して Microsoft Antimalware for Virtual Machines and Cloud Services](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)を構成するか、コード[サンプルを使用する](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|[監視を有効にするには、Microsoft Antimalware for Virtual Machines](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets)および Cloud Services with Azure PowerShell コマンドレットを使用します。 また、Azure Active Directory の利用状況レポートを確認して、疑わしい[][]アクティビティ (感染の可能性があるデバイスレポートを含む) を確認し[、MICROSOFT Defender Antivirus][]イベントを報告し、そのツールを AAD のアプリとして追加するように SIEM ツールを構成することもできます。

1. <span id="fn1" />クラウドによる保護に関連する一部の機能と機能の可用性は、Microsoft Endpoint Manager (Current Branch) と System Center 2012 Configuration Manager で異なります。 このライブラリでは、Windows 10、Windows Server 2016、および Microsoft Endpoint Manager (Current Branch) に焦点を当てました。 主 [な違いについては、「Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md) で Microsoft クラウド提供の保護を使用する」を参照してください。 [(テーブルに戻る)](#ref2)
  
2.  <span id="fn2" />Windows 10 では、Microsoft Defender Antivirus は、追加のクライアントまたはサービスをインストールまたは展開せずに使用できるコンポーネントです。 サードパーティのウイルス対策製品がアンインストールまたは古い[(Windows Server 2016](microsoft-defender-antivirus-on-windows-server.md)を除く) 場合、自動的に有効になります。 したがって、従来の展開は必要ありません。 ここでの展開とは、エンドポイントまたはサーバーで Microsoft Defender ウイルス対策コンポーネントが使用可能で有効になっているか確認する方法を指します。 [(テーブルに戻る)](#ref2)

3. <span id="fn3" />製品および保護更新プログラムの構成を含む機能と保護の構成については、このライブラリの [「Microsoft Defender ウイルス](configure-notifications-microsoft-defender-antivirus.md) 対策機能の構成」セクションでさらに説明します。 [(テーブルに戻る)](#ref2)

[エンドポイント保護ポイント サイト システムの役割]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[既定のマルウェア対策ポリシーとカスタマイズされたマルウェア対策ポリシー]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[クライアント管理]:  /configmgr/core/clients/manage/manage-clients
[カスタム クライアント設定でエンドポイント保護を有効にする]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
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
[Windows Defender WMIv2 プロバイダー]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Defender モジュールで使用できる Get- コマンドレット]: /powershell/module/defender/
[Microsoft Defender ウイルス対策の更新オプションを構成する]: manage-updates-baselines-microsoft-defender-antivirus.md
[機能Windows Defender構成する]: configure-microsoft-defender-antivirus-features.md
[設定またはポリシーが適用されていないかどうかを判断するグループ ポリシー]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[感染している可能性のあるデバイス]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Microsoft Defender ウイルス対策イベント]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>このセクションの内容

トピック | 説明
---|---
[Microsoft Defender ウイルス対策保護の展開と有効化](deploy-microsoft-defender-antivirus.md) | クライアントは Windows 10 のコアパーツとしてインストールされ、従来の展開は適用されませんが、Microsoft Endpoint Configuration Manager、Microsoft Intune、またはグループ ポリシー オブジェクトを使用してエンドポイントでクライアントを有効にする必要があります。 
[Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する](manage-updates-baselines-microsoft-defender-antivirus.md) | Microsoft Defender ウイルス対策の更新には、エンドポイントでのクライアントの更新 (製品の更新) とセキュリティ インテリジェンス (保護更新プログラム) の更新の 2 つの部分があります。 Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell、WMI を使用して、さまざまな方法でセキュリティ インテリジェンスを更新できます。
[Microsoft Defender ウイルス対策保護の監視とレポート](report-monitor-microsoft-defender-antivirus.md) | Microsoft Intune、Microsoft Endpoint Configuration Manager、Microsoft Operations Management Suite の更新コンプライアンス アドイン、またはサード パーティの SIEM 製品 (Windows イベント ログを使用) を使用して、保護状態を監視し、エンドポイント保護に関するレポートを作成できます。