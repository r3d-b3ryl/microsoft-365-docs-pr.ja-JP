---
title: Microsoft 365 を使用したハイブリッドワーク用のインフラストラクチャを設定する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-overview
- M365initiative-coredeploy
ms.custom: seo-marvel-jun2020
keywords: 在宅勤務、在宅勤務、ハイブリッド、リモート ワーカー、ハイブリッド ワーク、リモート従業員、ハイブリッド接続、リモート アクセス、在宅勤務、テレワーク、テレワーク、モバイル ワーク、リモート ジョブ、どこからでも作業、柔軟な職場
description: ハイブリッド ワーカーがオンプレミスおよび Microsoft 365 のリソースに安全にアクセスできるように、インフラストラクチャのレイヤーをステップ スルーします。
ms.openlocfilehash: 3eb70d99e44f296144ea9fa9c79ffd41475888ef
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61871913"
---
# <a name="set-up-your-infrastructure-for-hybrid-work-with-microsoft-365"></a>Microsoft 365 を使用したハイブリッドワーク用のインフラストラクチャを設定する

従業員の生産性とコラボレーションをセキュリティで保護して最適化するには、オンプレミスとリモートのワーカーが組織のオンプレミスおよびクラウドベースの情報、ツール、リソースに簡単かつ安全にアクセスできるようにする必要があります。 このソリューションは、従業員がどこにいても最高の仕事を行えるようにするインフラストラクチャの主要なレイヤーの展開を段階的に実行します。

ハイブリッドワーカーは、場所を組み合わせてオンサイトまたはリモートで作業できます。 多くの組織にとって、ワーカーが伝統的なオフィスから離れて仕事ができるようにすることは、以下のために重要です。

- 再配置を望まない、または柔軟な作業環境を必要とする従業員を雇用および維持する。
- ワーカーの通勤時間を減らして、生産的な時間を確保し、仕事以外でのストレス軽減のための時間を確保する。
- オフィス スペースの節約。

Microsoft 365 には、ハイブリッド ワーカーがオンサイトまたはリモートで作業できるようにする機能があります。

![Microsoft 365 を使用してハイブリッド ワーカーを強化します。](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)

> [!NOTE]
> Microsoft 365 を初めて使用する場合は、[こちらのリソース](https://www.microsoft.com/microsoft-365) を参照してください。

このビデオでは、展開プロセスの概要について説明します。
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4F1af]

オンサイトおよびクラウド ベースのインフラストラクチャを管理してハイブリッド ワーカーの生産性を向上させる IT プロフェッショナル向けに、このソリューションは次の主要な機能を提供します。

- 接続しました

  世界中のどこからでも、いつでも、ワーカーたちは以下にアクセスできます。

  - Microsoft 365 サブスクリプションのクラウドベースのサービスとデータ。

  - オンプレミスのアプリケーション データセンターで提供されるような組織のリソース。

- セキュリティ保護

  サインインは、多要素認証 (MFA) や Microsoft 365 と Windows 11 または 10 の組み込みセキュリティ機能により、マルウェア、悪意のある攻撃、データ損失から保護されています。

- 管理対象

  ハイブリッド ワーカーのデバイスは、、システム正常性への準拠を要求するために、セキュリティ設定を備えた許可されたアプリを介して、クラウドから管理されます。

- 共同作業と生産性

  ハイブリッド ワーカーは、次の高度な共同作業の手法により、オンプレミスと同じように生産性を高めることができます。

  - Teams を使用したオンライン会議とチャット セッション。

  - SharePoint と OneDrive を使用してグローバルなアクセシビリティとリアルタイムの共同作業を実現する、クラウドベースのファイル ストレージ用の共有ワークスペース。

  - 作業を分割して完了するための共有タスクとワークフロー。

シームレスなサインイン エクスペリエンスを実現するには、オンプレミスの Active Directory ドメイン サービス (AD DS) のユーザー アカウントを Azure Active Directory (Azure AD) と同期する必要があります。 Windows 11 または 10 デバイスを保護するには、そのデバイスを Intune に登録する必要があります。 インフラストラクチャの概要を次に示します。

![ハイブリッド ワーカー向けの Microsoft 365 の基本インフラストラクチャ。](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

ハイブリッド ワーカーに対して Microsoft 365 の機能を有効にするには、これらの Microsoft 365 機能を使用します。

|機能|説明|ライセンス|
|---|---|---|
|セキュリティの既定値が適用されている MFA|サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。|Microsoft 365 E3 または E5|
|条件付きアクセスが適用されている MFA|条件付きアクセス ポリシーを使用したサインインのプロパティに基づいて MFA を要求します。|Microsoft 365 E3 または E5|
|リスクベースの条件付きアクセスが適用されている MFA|Azure AD Identity Protection によるユーザー サインインのリスクに基づいて MFA を要求します。|Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3|
|セルフサービスによるパスワードのリセット (SSPR)|ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。|Microsoft 365 E3 または E5|
|Azure AD アプリケーション プロキシ|イントラネット サーバーでホストされている Web ベースのアプリケーションに安全なリモート アクセスを提供します。|別の有料 Azure サブスクリプションが必要|
|Azure ポイント対サイト VPN|Azure 仮想ネットワークを介してリモート ワーカーのデバイスからイントラネットへの安全な接続を作成します。|別の有料 Azure サブスクリプションが必要|
|Windows 365|Windows 365 Cloud PC で、個人用デバイスや管理されていないデバイスしか使用できないリモート ワーカーをサポートします。|別の有料 Azure サブスクリプションが必要|
|リモート デスクトップ |従業員によるイントラネット上の Windows ベースのコンピューターへの接続を許可します。|Microsoft 365 E3 または E5|
|リモート デスクトップ サービス ゲートウェイ|通信を暗号化し、RDS ホストがインターネットに直接公開されないようにします。|別の Windows サーバー ライセンスが必要|
|Microsoft Intune|デバイスとアプリケーションを管理します。|Microsoft 365 E3 または E5|
|構成マネージャーを使用するための|デバイスでのソフトウェアのインストール、更新、設定を管理します|別の Configuration Manager ライセンスが必要|
|エンドポイントの分析|Windows クライアントの更新プログラムの準備状況を確認します。|別の Configuration Manager ライセンスが必要|
|Windows Autopilot|生産的に使用するために、新しい Windows 11 または 10 デバイスをセットアップして事前構成します。|Microsoft 365 E3 または E5|
|Microsoft Teams、Exchange Online、SharePoint Online、OneDrive、Microsoft 365 アプリ、Microsoft Power Platform、Yammer|作成、連絡、共同作業を行います。|Microsoft 365 E3 または E5|
||||

セキュリティとコンプライアンスの基準については、「[リモート ワーカーのためのセキュリティとコンプライアンスの展開](empower-people-to-work-remotely-security-compliance.md)」を参照してください。

<a name="poster"></a> このソルーションを 2 ページにまとめた [「ハイブリッド ワーカーを支援するポスター」](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf) を参照してください。

[![ハイブリッド ワーカーのポスターを強化します。](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](https://download.microsoft.com/download/9/b/b/9bb5fa79-74e9-497b-87c5-4021e53d9fc2/hybrid-worker-infrastructure.pdf)

## <a name="provide-hybrid-working-for-all-of-your-workers"></a>すべてのワーカーにハイブリッド ワークを提供する

これらのデバイスを使用すると、すべての従業員がどこからでも生産性を維持できるようになります。

- Web 経由で直接 Microsoft 365 クラウド アプリやサービスにアクセスするための機能、セキュリティ、パフォーマンスが備わった Surface ノート PC や Windows 11 または 10 などの最新のデバイス。

- 自宅で使用されている古いノート PC やデスクトップなど [Windows 365 クラウド PC](empower-people-to-work-remotely-remote-access.md#deploy-windows-365-to-provide-remote-access-for-remote-workers-using-personal-devices) を介して間接的に Microsoft 365 クラウド アプリやサービスにアクセスできるすべてのデバイス。 このオプションは、高い性能、強力なセキュリティ、およびシンプルな IT 管理を提供します。

## <a name="next-steps"></a>次の手順

次の手順を実行することにより、組織のサーバー、クラウド サービスへのアクセスをセキュリティで保護して最適化し、リモート ワーカーの生産性を最大限に高めることができます。

1. [MFA を使用してリモート ワーカーのサインイン セキュリティを強化する](empower-people-to-work-remotely-secure-sign-in.md)
2. [オンプレミスのアプリとサービスへのリモート アクセスを提供する](empower-people-to-work-remotely-remote-access.md)
3. [セキュリティおよびコンプライアンスの展開](empower-people-to-work-remotely-security-compliance.md)
4. [デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する](empower-people-to-work-remotely-manage-endpoints.md)
5. [ハイブリッド ワーカー生産性向上アプリとサービスを展開する](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [ワーカーをトレーニングし、使用状況のフィードバックに対処する](empower-people-to-work-remotely-train-monitor-usage.md)

[![Microsoft 365 を使用したハイブリッド ワーク用のインフラストラクチャを設定する手順。](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)](empower-people-to-work-remotely-secure-sign-in.md)

架空ではあるものの、代表的な多国籍組織がハイブリッド ワーク用のインフラストラクチャをどのように設定したかを確認するハイブリッド ワーク向けの 「[Contoso の COVID-19 対応](contoso-remote-onsite-work.md)」を参照してください。
