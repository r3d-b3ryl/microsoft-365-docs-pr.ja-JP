---
title: Windows 10 Enterprise のセキュリティ機能を展開する
description: Microsoft 365 Enterprise の一部として Windows 10 Enterprise を PC に展開するために必要な手順の、詳しいガイダンスです。
keywords: microsoft 365、microsoft 365 Enterprise、microsoft 365 ドキュメント、Windows 10 enterprise、security
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: 60145444a7fb2b4ddf2ea6a3606e04aa04a578af
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291624"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>手順 5: Windows 10 Enterprise のセキュリティ機能を展開する

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 では、エンタープライズユーザーの保護、脅威の停止、データ損失の防止のためのセキュリティ機能が提供されています。 

これらのテクノロジの詳細については、以下を参照してください。
* [id 保護](https://docs.microsoft.com/windows/security/identity-protection/)-Windows Hello for business、Credential Guard、およびアクセス制御について説明します。
* [脅威保護](https://docs.microsoft.com/windows/threat-protection/)-Windows Defender Advanced Threat protection、予防的保護のための統合プラットフォーム、ブリーチ後の検出、自動調査、および応答について説明します。
* [情報保護](https://docs.microsoft.com/windows/security/information-protection/)-windows 10 がエンタープライズデータを保護するために使用する BitLocker、windows 情報保護、およびその他の方法について説明します。 

この手順では、以下のセキュリティ機能を使用して、を展開、管理、構成、およびトラブルシューティングする方法を示します。

* [Windows Defender ウイルス対策](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Windows Defender Advanced Threat Protection](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender ウイルス対策
windows Defender ウイルス対策 (AV) は、windows 10 に組み込まれているマルウェア対策ソリューションです。 デスクトップ、ポータブルコンピューター、およびサーバーのセキュリティとマルウェア対策の管理を提供します。 windows defender AV、最小要件、およびこの機能を管理する方法の詳細については、「windows [10 と windows Server 2016 の windows defender ウイルス対策](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)」を参照してください。

プライマリウイルス対策クライアントとして windows defender AV を使用していない場合、または windows defender ATP を使用している場合は、いくつかの考慮事項を考慮する必要があります。 詳細については、「 [Windows Defender AV 互換性](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)」を参照してください。

### <a name="deployment-and-management"></a>展開と管理
Windows Defender AV を展開および管理するには、次のガイダンスに従ってください。

* [Windows Defender AV の展開、管理、およびレポート](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [管理および構成ツールのリファレンストピック](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>構成
ユーザーは、いくつかの機能を構成できます。 詳細については、以下のリソースを参照してください。

* [Windows Defender AV 機能を構成する](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [管理および構成ツールのリファレンストピック](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

構成オプションの詳細については、「グループポリシーの構成によって定義されたすべての設定の一覧を表示する」を参照してください。[グループポリシー設定を使用して Windows Defender AV を構成および管理する](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

[windows defender av 保護評価ガイド](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus)を使用すると、ネットワーク上の windows defender av の保護レベルと影響を評価するのに役立ちます。 これは、初期構成を作成したり、' クイックスタートガイド ' として使用したりする場合にも役立ちます。また、機能を構成および有効にして最大限の保護を実現するための推奨事項を提示するように定期的に更新されています。

### <a name="reporting"></a>Reporting
System Center configuration Manager、Microsoft Intune などの構成ツールを使用してレポートを取得できます。 また、更新プログラムのコンプライアンス (OMS) または SIEM で Windows イベントログを使用してレポートを取得することもできます。 windows defender ATP のライセンスを所有している場合は、windows defender AV 検出にレポートを取得し、基本的な修復を実行することもできます。 詳細については、以下のリソースを参照してください。
* [Windows Defender AV の展開、管理、およびレポート](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Windows Defender AV protection に関するレポート](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Windows Defender ATP ポータルの概要](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>トラブルシューティング
エラーおよびイベントコードの基本的なトラブルシューティングの詳細については、「[イベントログとエラーコードを確認する」を参照して、Windows Defender AV の問題のトラブルシューティングを](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)行ってください。

Windows Defender セキュリティインテリジェンス送信システムを使用して、問題 (誤検知など) を送信することもできます。 その方法については、「 [Microsoft に問題を提出](https://www.microsoft.com/wdsi/filesubmission)する」を参照してください。

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
windows Defender Exploit Guard は、windows 10 の一連の新しいホスト侵入防止機能です。 windows defender exploit guard の詳細、最小要件、およびこの機能を管理する方法については、「 [windows defender exploit guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)」を参照してください。

### <a name="deployment-management-and-configuration"></a>展開、管理、および構成
Windows Defender Exploit Guard を展開、管理、および構成するには、次のガイダンスに従ってください。
* [Exploit protection](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [アタック領域の保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [ネットワーク保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [フォルダーアクセスの制御](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

一連の評価トピックを使用して、ネットワークに対する Windows Defender Exploit Guard の保護レベルと影響を評価することができます。 これは、初期構成を作成したり、' クイックスタートガイド ' として使用したりする場合にも役立ちます。また、トピックとガイダンスは定期的に更新されており、最大限の保護を確保するために、機能を構成して有効にするための最も役立つ推奨事項を提供します。 詳細については、 [Windows Defender Exploit Guard を評価](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)してください。

### <a name="reporting"></a>Reporting
System Center configuration Manager または Intune などの構成ツールを使用してレポートを取得することができます。 SIEM で Windows イベントログを使用してレポートを取得することもできます。 windows defender ATP のライセンスを所有している場合は、windows defender AV 検出にレポートを取得し、基本的な修復を実行することもできます。 詳細については、以下のリソースを参照してください。
* [Windows Defender Exploit Guard イベントを表示する](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Windows Defender ATP ポータルの概要](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>トラブルシューティング
基本的なトラブルシューティングを実行したり、必要に応じて Microsoft に .cab ファイルを提供したり、Windows Defender セキュリティインテリジェンス送信システムを使用して問題 (誤検知など) を送信したりすることができます。 その方法については、「 [Microsoft に問題を提出](https://www.microsoft.com/wdsi/filesubmission)する」を参照してください。


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Windows Defender Advanced Threat Protection
Windows Defender ATP は、Microsoft 365 Enterprise E5 プランでのみ利用できます。これは、企業のお客様が自社のネットワーク上の高度な脅威を検出、調査、および対応することを可能にするセキュリティサービスです。 Windows Defender ATP、最小要件、およびこの機能を管理する方法の詳細については、以下を参照してください。

* [Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [最小要件](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>展開、管理、および構成
windows Defender ATP を展開するには、適切な windows ライセンスを持っていることを確認する必要があります。 適切なライセンスを持っていることを確認したら、データを格納する場所の地理位置情報を決定する必要があります。 その後、サービスのオンボードエンドポイントを開始できます。

これらの手順の詳細については、次の主要なトピックを参照してください。 

* [ライセンスのプロビジョニングを検証し、セットアップを完了する](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [データの保存とプライバシー](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [オンボードエンドポイントとセットアップアクセス](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>検出、調査、応答
エンドポイントがサービスに正常にオンボードされた後、さまざまなダッシュボードからの警告の調査を開始できます。 通知を調査した後は、通知に対する応答アクションを実行できます。 

これらの方法の詳細については、以下を参照してください。
* [Windows Defender ATP ポータルの概要](https://go.microsoft.com/fwlink/?linkid=861596)
* [Windows Defender ATP ポータルを使用する](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [応答アクションを実行する](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>他の製品とツールと統合する
Windows Defender ATP は、セキュリティ機能を拡張するために、さまざまな他の製品とツールを統合し、サポートしています。 

ツールおよびその他の製品の詳細については、以下を参照してください。
* [SIEM ツール](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [カスタム通知を作成する](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [api を使用する](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [power BI レポートを作成する](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>トラブルシューティング
オンボードまたは製品の使用中に問題が発生することがあります。 問題に対処する方法の詳細については、以下を参照してください。
* [オンボード問題のトラブルシューティング](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Windows Defender ATP のトラブルシューティング](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>次の手順

[Windows 10 Enterprise infrastructure の終了条件](windows10-exit-criteria.md)
