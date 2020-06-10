---
title: Microsoft 365 でリモート ワーカーを支援する
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
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
ms.openlocfilehash: 763c8e745eb54897c1df88ecb5a9064987ed5a13
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560464"
---
# <a name="empower-remote-workers-with-microsoft-365"></a>Microsoft 365 でリモート ワーカーを支援する

組織のオンプレミスおよびクラウドベースの情報、ツール、リソースに、ワーカーが自宅から安全にアクセスできるようにすることが必要になる場合があります。 多くの組織にとって、ワーカーがシームレスかつ安全にオフィスから離れて仕事ができるようにすることは、以下のために重要です。

- オフィス スペースの節約。
- 配置転換を望まないワーカーを雇用し、維持する。
- ワーカーの通勤時間を減らして、生産的な時間を確保し、仕事以外でのストレス軽減のための時間を確保する。

リモート作業 (テレワーキングとも呼ばれる) は、次のような範囲に及ぶ可能性があります。

- 会議やクライアント会議のために時々オフィスを離れるワーカー。
- リモートでフルタイムで働く一部のワーカー。
- オフィスがなく、すべてのワーカーがリモートで作業をする完全なリモートの組織。

世界中のどこからでも、いつでも、リモート ワーカーは以下にアクセスできる必要があります。

- オンプレミスのアプリケーション データセンターで提供されるような組織のリソース。
- Microsoft 365 サブスクリプションのクラウドベースのサービスとデータ (Teams、Exchange Online、SharePoint、OneDrive など)。

シームレスなサインイン エクスペリエンスを実現するには、Active Directory ドメイン サービス (AD DS) のユーザー アカウントを Azure Active Directory (Azure AD) と同期する必要があります。 Windows 10 デバイスを保護するには、そのデバイスを Intune に登録する必要があります。 インフラストラクチャの概要を次に示します。

![リモート ワーカー向けの Microsoft 365 の基本インフラストラクチャ](../media/empower-people-to-work-remotely/remote-workers-basic-infrastructure.png)


たとえば COVID-19 危機への対応として、リモート ワーカーをサポートするために、Microsoft 365 Enterprise の機能を組み合わせることで、次のような高度な共同作業が可能になります。

- オンライン会議およびチャット セッション。
- グローバルなアクセシビリティとリアルタイムのコラボレーションを実現する、クラウドベースのファイル ストレージ用の共有ワークスペース。
- 作業を分割して完了するための共有タスクとワークフロー。

セキュリティを強化するために、Microsoft 365 には以下が含まれます。

- 認証要件の適用、高リスクのサインインの検出と応答、選択したアプリと非準拠デバイスのブロック。
- クラウド内の暗号化された接続とデジタル資産。
- ファイルに対して誰が何を実行できるかを定義する権限。
- Windows 10 デバイスを保護する包括的なセキュリティ機能。

これらのリモート ワーカーの基準を満たすには、次の Microsoft 365 機能を使用します。

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

次の手順を実行することにより、組織のサーバー、データ、クラウド サービスへのアクセスをセキュリティで保護して最適化し、従業員の生産性を最大限に高めることができます。

1. [MFA を使用してリモート ワーカーのサインイン セキュリティを強化する](empower-people-to-work-remotely-secure-sign-in.md)
2. [オンプレミスのアプリとサービスへのリモート アクセスを提供する](empower-people-to-work-remotely-remote-access.md)
3. [デバイス、PC、およびその他のエンドポイントのエンドポイント管理を展開する](empower-people-to-work-remotely-manage-endpoints.md)
4. [リモート ワーカー向けの生産性向上アプリとサービスを展開する](empower-people-to-work-remotely-teams-productivity-apps.md)
5. [コミュニケーション会場を作成する](empower-people-to-work-remotely-communication-venues.md)
6. [リモート ワーカーをトレーニングし、使用状況のフィードバックに対処する](empower-people-to-work-remotely-train-monitor-usage.md)

![Microsoft 365 でリモート ワーカーを支援するための手順](../media/empower-people-to-work-remotely/remote-workers-step-grid.png)

リモート ワーカーのサポートに関する Microsoft の最新情報については、「[Enabling remote work Tech Community site (リモート ワークを可能にする技術コミュニティ サイト)](https://resources.techcommunity.microsoft.com/enabling-remote-work/)」を参照してください。
