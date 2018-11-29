---
title: Windows 10 Enterprise のセキュリティ機能を展開する
description: Microsoft 365 Enterprise の一部として Windows 10 Enterprise を PC に展開するために必要な手順の、詳しいガイダンスです。
keywords: Microsoft 365、Microsoft 365 エンタープライズでは、Microsoft 365、10 企業の Windows のドキュメントのセキュリティ
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d051f9e56d8e9986fbe0975c2bdc6c606b32a444
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869639"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>手順 5: Windows 10 Enterprise のセキュリティ機能を展開する

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 には、上の脅威、ヘルプから、デバイスをセキュリティで保護し、アクセス制御を支援するコンピューターを保護する機能が用意されています。 

これらのテクノロジの詳細についてを参照してください。
* [アクセスの保護](https://docs.microsoft.com/windows/access-protection/)についてはアクセス コントロールでは、S/MIME、デジタル証明書、資格情報の保護、ユーザー アカウント制御では、仮想スマート カード、Windows こんにちはビジネス、セキュリティが強化された Windows ファイアウォールなどの
* [デバイスのセキュリティ](https://docs.microsoft.com/windows/device-security/)の AppLocker の含まれています、BitLocker、デバイスの監視、およびトラステッド プラットフォーム モジュール
* [脅威の保護](https://docs.microsoft.com/windows/threat-protection/)- Windows Defender は、セキュリティ センター、Windows Defender の高度な脅威保護、Windows Defender のウイルス対策ソフトウェア、Windows Defender のアプリケーション保護、Windows Defender スマート画面、および Windows の情報保護

この手順は、どのようにすることができます展開、管理、構成、およびこれらのセキュリティ機能を使用してトラブルシューティングを示しています。

* [Windows Defender ウイルス対策](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Windows Defender Advanced Threat Protection](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender ウイルス対策
Windows Defender ウイルス対策ソフトウェア (AV) とは、10 の Windows に組み込まれているウイルス対策ソリューションです。デスクトップ、ポータブル コンピューター、およびサーバーのセキュリティとウイルス対策の管理を提供します。Windows Defender の AV、最低限の要件では、この機能を管理する方法に関する詳細情報は、 [Windows Defender の 10 の Windows および Windows Server 2016 のウイルス対策ソフトウェア](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)を参照してください。

主要なウイルス対策クライアントとして Windows Defender の AV を使用していない、またはいくつかの考慮事項がある場合、Windows Defender の分析ツールを使用する、考慮する必要があります。詳細については、 [Windows Defender の AV の互換性](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)を参照してください。

### <a name="deployment-and-management"></a>展開と管理
導入すると、Windows Defender の AV の管理、次のガイダンスは、ここを実行します。

* [展開、管理、および Windows Defender のアクセス違反の報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [管理/構成ツールのリファレンス トピック](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>構成
ユーザーは、さまざまな機能を構成できます。詳細については、これらのリソースを参照してください。

* [Windows Defender の AV 機能を構成します。](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [管理/構成ツールのリファレンス トピック](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

構成オプションを理解するためを参照してくださいこのすべての設定の一覧で定義された、グループ ポリシーの構成):[グループ ポリシーを使用して設定を構成し、Windows Defender の AV を管理するには](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

[Windows Defender のウイルス対策保護評価ガイド](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus)を使用すると、保護レベルと、ネットワーク上の Windows Defender の AV の影響を評価します。これ初期構成を作成するか、クイック スタート ガイドとして役立つことができ、定期的に更新を構成して、最大限の保護を確保する機能を有効にするための最も役に立つ推奨事項を提供します。

### <a name="reporting"></a>レポート
システム センター構成マネージャーまたは Microsoft Intune のような構成ツールを使用してレポートを取得できます。更新コンプライアンス (OMS) から、または、SIEM の Windows イベント ログを使用してのレポートを取得することもできます。Windows Defender の ATP のライセンスを所有する場合も Windows Defender のアクセス違反の検出にレポートを取得し、基本的な修復を実行します。詳細については、これらのリソースを参照してください。
* [展開、管理、および Windows Defender のアクセス違反の報告](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Windows Defender のウイルス対策保護を報告します。](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Windows Defender の ATP のポータルの概要](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>トラブルシューティング
エラーとイベントのコードの基本的なトラブルシューティングの情報は、[イベント ログを確認しエラー コードが Windows Defender の AV に関する問題のトラブルシューティング](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)を参照してください。

Windows Defender セキュリティ インテリジェンスの送信システムを使用して (誤) などの問題を送信することもできます。学習する方法については、[マイクロソフトに送信の問題](https://www.microsoft.com/wdsi/filesubmission)を参照してください。

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
Windows Defender を悪用する可能性のガードは、Windows の 10 のホスト侵入防止の機能の新しいセットです。Windows Defender を悪用するガード、最低限の要件では、この機能を管理する方法に関する詳細情報は、 [Windows Defender を悪用するガード](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)を参照してください。

### <a name="deployment-management-and-configuration"></a>展開、管理、および構成
展開、管理、および Windows Defender を悪用するガードを構成する、次のガイダンスは、ここを実行します。
* [脆弱性の保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [攻撃の表面の保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [ネットワークの保護](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [フォルダーへのアクセスを制御](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

一連のトピックの評価を使用すると、保護レベルと、ネットワーク上の Windows Defender を悪用するガードの影響を評価します。便利なは、初期構成を作成するか、クイック スタート ガイドとしてこのことができ、トピックとガイダンスが最も役に立つ推奨事項を提供するを構成して、最大限の保護を確保する機能を有効にするために定期的に更新します。詳細については、[ガードを悪用する Windows Defender を評価](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)します。

### <a name="reporting"></a>レポート
システム センター構成マネージャーまたは Intune のような構成ツールを使用してレポートを取得できます。SIEM の Windows イベント ログを使用してレポートを取得することもできます。Windows Defender の ATP のライセンスを所有する場合も Windows Defender のアクセス違反の検出にレポートを取得し、基本的な修復を実行します。詳細については、これらのリソースを参照してください。
* [Windows Defender を悪用するガードのイベントを表示します。](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Windows Defender の ATP のポータルの概要](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>トラブルシューティング
基本的なトラブルシューティングを実行または必要に応じての .cab ファイルを使用してマイクロソフトが提供して (誤) などの問題を Windows Defender セキュリティ インテリジェンスの送信システムを使用して送信します。学習する方法については、[マイクロソフトに送信の問題](https://www.microsoft.com/wdsi/filesubmission)を参照してください。


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Windows Defender Advanced Threat Protection
Windows Defender の ATP、マイクロソフト 365 エンタープライズ E5 プランでのみ利用可能とは、検出、調査、および、ネットワーク上の高度な脅威に対応する企業のお客様を有効にするセキュリティ サービスです。Windows Defender の ATP、最低限の要件では、この機能を管理する方法に関する詳細についてを参照してください。

* [Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [最小要件](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>展開、管理、および構成
Windows Defender の分析ツールを展開するには、右の Windows のライセンスがあることを確認する必要があります。右側のライセンスがあることを確認した後、データが格納される場所の地理位置情報を決定する必要があります。その後は、契約時のエンドポイントをサービスを開始できます。

次の手順の詳細については、これらの主要なトピックを参照してください。 

* [ライセンスのプロビジョニングを検証し、設定を完了](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [データ記憶域とプライバシー](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [オンボードのエンドポイント、およびアクセスのセットアップ](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>検出、調査、対応
正常に契約時に、サービス、エンドポイントの後、さまざまなダッシュ ボードからのアラートを調査を開始できます。アラートを調査して後、は、警告の応答のアクションを実行できます。 

これらを行う方法の詳細についてを参照してください。
* [Windows Defender の ATP のポータルの概要](https://go.microsoft.com/fwlink/?linkid=861596)
* [Windows Defender の ATP のポータルを使用します。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [応答アクションを実行します。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>他の製品やツールとの統合します。
Windows Defender の分析ツールは、統合し、さまざまなその他の製品とそのセキュリティ機能を拡張するためのツールをサポートしています。 

ツールおよびその他の製品の詳細についてを参照してください。
* [SIEM ツール](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [カスタム通知を作成します。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Api を使用します。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [電源の BI レポートを作成します。](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>トラブルシューティング
契約時または製品の使用中に問題が発生する可能性があります。問題に対処する方法の詳細についてを参照してください。
* [契約時の問題のトラブルシューティング](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Windows Defender の分析ツールのトラブルシューティング](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>次の手順

[Windows 10 Enterprise のインフラストラクチャ終了条件](windows10-exit-criteria.md)
