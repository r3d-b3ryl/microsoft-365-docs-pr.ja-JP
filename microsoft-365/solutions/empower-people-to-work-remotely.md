---
title: Microsoft 365 でリモート ワーカーを支援する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 07/14/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: ワーカーがいつでもどこからでもリモートで作業できるようにするセキュリティとサービスのインフラストラクチャを構成します。
ms.openlocfilehash: 58915d80d9eb81009632971bbfc84a7b681e125e
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158900"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Microsoft 365 でリモート ワーカーを支援する

組織のオンプレミスおよびクラウドベースの情報、ツール、リソースに、ワーカーが自宅から安全にアクセスできるようにすることが必要になる場合があります。 多くの組織にとって、ワーカーがオフィスから離れて仕事ができるようにすることは、以下のために重要です。

- オフィス スペースの節約。
- 配置転換を望まないワーカーを雇用し、維持する。
- ワーカーの通勤時間を減らして、生産的な時間を確保し、仕事以外でのストレス軽減のための時間を確保する。

Microsoft 365 には、ワーカーがリモートで作業できるようにするための機能があります。

![Microsoft 365 でリモート ワーカーを支援する](../media/empower-people-to-work-remotely/2-m365-remoteworker-solution-businessoverview.png)


| | |
|:-------|:-----|
| 接続しました | 世界中のどこからでも、いつでも、リモート ワーカーは以下にアクセスできます。 <ul><li>Microsoft 365 サブスクリプションのクラウドベースのサービスとデータ。 </li><li>オンプレミスのアプリケーション データセンターで提供されるような組織のリソース。</li></ul> |
| セキュリティ保護 | サインインは、多要素認証 (MFA) や Microsoft 365 と Windows 10 の組み込みセキュリティ機能により、マルウェア、悪意のある攻撃、データ損失から保護されています。 |
| 管理対象 | リモート ワーカーのデバイスは、許可されたアプリを介して、セキュリティ設定を備えたクラウドから管理され、システム正常性への準拠を要求します。 |
| 共同作業と生産性 | リモート ワーカーは、次の高度な共同作業の手法により、オンプレミスと同じように生産性を高めることができます。 <ul><li>Teams を使用したオンライン会議とチャット セッション。 </li><li>SharePoint と OneDrive を使用してグローバルなアクセシビリティとリアルタイムの共同作業を実現する、クラウドベースのファイル ストレージ用の共有ワークスペース。 </li><li>作業を分割して完了するための共有タスクとワークフロー。 </li></ul> |
|||

シームレスなサインイン エクスペリエンスを実現するには、オンプレミスの Active Directory ドメイン サービス (AD DS) のユーザー アカウントを Azure Active Directory (Azure AD) と同期する必要があります。 Windows 10 デバイスを保護するには、そのデバイスを Intune に登録する必要があります。 インフラストラクチャの概要を次に示します。

![リモート ワーカー向けの Microsoft 365 の基本インフラストラクチャ](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)

リモート ワーカーの基準を満たすには、次の Microsoft 365 機能を使用します。

| 機能 | 説明 | ライセンス |
|:-------|:-----|:-------|
| セキュリティの既定値が適用されている MFA   | サインインには、2 つ目の認証形式を要求することで、ID とデバイスを侵害から保護します。セキュリティの既定値では、すべてのユーザー アカウントに MFA が必要です。   | Microsoft 365 E3、E5 |
| 条件付きアクセスが適用されている MFA| 条件付きアクセス ポリシーを使用したサインインのプロパティに基づいて MFA を要求します。    | Microsoft 365 E3、E5 | 
| リスクベースの条件付きアクセスが適用されている MFA   | Azure Advanced Threat Protection によるユーザー サインインのリスクに基づいて MFA を要求します。 | Azure AD Premium P2 ライセンスを含む Microsoft 365 E5 または E3 | 
| セルフサービスによるパスワードのリセット (SSPR)    | ユーザーによるパスワードまたはアカウントのリセットまたはロック解除を許可します。  | Microsoft 365 E3、E5 |
| Azure AD アプリケーション プロキシ    | イントラネット サーバーでホストされている Web ベースのアプリケーションに安全なリモート アクセスを提供します。   | 別の有料 Azure サブスクリプションが必要 |
| Azure ポイント対サイト VPN   | Azure 仮想ネットワークを介してリモート ワーカーのデバイスからイントラネットへの安全な接続を作成します。   | 別の有料 Azure サブスクリプションが必要 |
| Windows Virtual Desktop   | Azure で実行されている仮想デスクトップで、個人の管理されていないデバイスのみを使用できるリモート ワーカーをサポートします。 | 別の有料 Azure サブスクリプションが必要 |
| リモート デスクトップ サービス (RDS) | 従業員によるイントラネット上の Windows ベースのコンピューターへの接続を許可します。 | Microsoft 365 E3、E5 | 
| リモート デスクトップ サービス ゲートウェイ   | 通信を暗号化し、RDS ホストがインターネットに直接公開されないようにします。 | 別の Windows サーバー ライセンスが必要 |
| Microsoft Intune | デバイスとアプリケーションを管理します。   | Microsoft 365 E3、E5 | 
| Configuration Manager | デバイスでのソフトウェアのインストール、更新、設定を管理します | 別の Configuration Manager ライセンスが必要 |
| Desktop Analytics | Windows クライアントの更新プログラムの準備状況を確認します。   | 別の Configuration Manager ライセンスが必要 |
| Windows Autopilot | 生産的に使用するために、新しいWindows 10デバイスをセットアップして事前構成します。   | Microsoft 365 E3、E5 |
| Microsoft Teams、Exchange Online、SharePoint Online、OneDrive、Microsoft 365 アプリ、Microsoft Power Platform、Yammer、Power Apps | 作成、連絡、共同作業を行います。 | Microsoft 365 E3、E5 |
||||

<a name="poster"></a> このシナリオを 2 ページにまとめた [「リモート ワーカーを支援するポスター」](../downloads/empower-remote-workers.pdf) を参照してください。

[![リモート ワーカーを支援するポスター](../media/empower-people-to-work-remotely/empower-remote-workers-poster.png)](../downloads/empower-remote-workers.pdf)

このポスターを [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pdf) または [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/empower-remote-workers.pptx) 形式でダウンロードして、レター、リーガル、タブロイド (11 x 17) のサイズの紙に印刷することもできます。

次の手順を実行することにより、組織のサーバー、データ、クラウド サービスへのアクセスをセキュリティで保護して最適化し、従業員の生産性を最大限に高めることができます。

1. [MFA を使用してリモート ワーカーのサインイン セキュリティを強化する](empower-people-to-work-remotely-secure-sign-in.md)
2. [オンプレミスのアプリとサービスへのリモート アクセスを提供する](empower-people-to-work-remotely-remote-access.md)
3. [セキュリティおよびコンプライアンスの展開](empower-people-to-work-remotely-security-compliance.md)
4. [デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する](empower-people-to-work-remotely-manage-endpoints.md)
5. [リモート ワーカー向けの生産性向上アプリとサービスを展開する](empower-people-to-work-remotely-teams-productivity-apps.md)
6. [リモート ワーカーをトレーニングし、使用状況のフィードバックに対処する](empower-people-to-work-remotely-train-monitor-usage.md)

![Microsoft 365 でリモート ワーカーを支援するための手順](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

リモート ワーカーのサポートに関する Microsoft の最新情報については、「[Enabling remote work Tech Community site (リモート ワークを可能にする技術コミュニティ サイト)](https://resources.techcommunity.microsoft.com/enabling-remote-work/)」を参照してください。
