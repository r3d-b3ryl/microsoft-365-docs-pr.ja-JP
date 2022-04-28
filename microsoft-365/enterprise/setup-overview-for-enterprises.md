---
title: 組織のMicrosoft 365 Enterpriseを展開する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/19/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-subscription-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.assetid: ee73dafb-be54-492e-bcfd-0fbfb5f65e94
description: これらの概要手順は、ネットワークの設定、ID の作成、Microsoft 365 Appsのデプロイ、データの移行に役立ちます。
ms.openlocfilehash: 216a06cbd8291bfe01944b01de45f3fce6908b05
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091547"
---
# <a name="deploy-microsoft-365-enterprise-for-your-organization"></a>組織のMicrosoft 365 Enterpriseを展開する

Microsoft 365 Enterpriseをデプロイし、それをオンプレミス インフラストラクチャと統合し、従業員がクラウドベースの生産性とコラボレーションを利用できるようにする準備はできましたか?

この記事では、2 つのデプロイ オプションについて説明します。 いずれの場合も、Microsoft はデプロイの成功に向けて従うためのガイド付きパスを提供します。

## <a name="guided-microsoft-365-enterprise-setup-process-with-fasttrack"></a>FastTrackを使用したガイド付きMicrosoft 365 Enterpriseセットアップ プロセス

**[Microsoft 365のFastTrack](https://www.microsoft.com/fasttrack/microsoft-365)** は、Microsoft 365をデプロイするための最適な方法です。 FastTrack を使用すると、最も一般的な展開を構成する手順が表示され、質問に回答しながら構成できます。 

一連のセットアップ ガイドにアクセスするには、Microsoft 365 サブスクリプションにサインインし、[セットアップ ガイダンス](https://aka.ms/o365fasttrack)に移動します。

>[!Note]
>[Microsoft パートナー](https://www.microsoft.com/solution-providers/home)からヘルプを受けることもできます。
>

## <a name="do-it-yourself-guided-deployment-of-microsoft-365-enterprise"></a>Microsoft 365 Enterpriseの Do-it-it-yourself ガイド付きデプロイ

Microsoft 365 Enterpriseを独自にデプロイするには、詳細な調査を実行して、サービス構成とユーザー導入Microsoft 365効率化する設計上の決定を行う必要があります。 [ここで](get-your-organization-ready-for-office-365.md)計画を開始します。

計画の完了後にMicrosoft 365 Enterpriseを独自にデプロイするには、次の手順をお勧めします。

1. [ネットワークをセットアップする](set-up-network-for-microsoft-365.md)

   インターネット ドメインの追加と、オンプレミス ユーザーのネットワーク パフォーマンスの最適化が含まれます。
 
2. [ID を設定する](protect-your-global-administrator-accounts.md)

   ID モデル (クラウド専用またはハイブリッド) の決定と、ハイブリッド ID の場合は、オンプレミスの Active Directory Domain Services (AD DS) とMicrosoft 365 サブスクリプションの間のディレクトリ同期の設定が含まれます。

3. [セキュリティを実装する](/office365/securitycompliance/security-roadmap)

   最初の 30 日間、90 日間、およびそれ以降のテナントと ID の基本的なセキュリティ、脅威、および情報保護の構成とロールアウトが含まれます。
 
4. [クライアント ソフトウェアを展開する](/DeployOffice/deployment-guide-microsoft-365-apps)

   デバイスへのMicrosoft 365 Apps for enterprise (以前の名前付きOffice 365 ProPlus)、クラウドで更新され、常に最新バージョンのOffice スイート (Word、Excel、PowerPointなど) の展開が含まれます。 すべてのMicrosoft 365クライアント ライセンスには、Microsoft 365 Apps for enterprise用のライセンスが含まれています。
 
5. [モバイル デバイス管理を設定する](https://support.office.com/article/set-up-mobile-device-management-mdm-in-office-365-dd892318-bc44-4eb1-af00-9db5430be3cd)

   Microsoft 365 Enterpriseには、ユーザーのモバイル デバイスのセキュリティ保護と管理に役立つモバイル デバイス管理機能が含まれています。
 
6. [サービスとアプリケーションを構成する](configure-services-and-applications.md)

   データの移行に関する情報と、Exchange Online、SharePoint Online、Teamsなどの主要なMicrosoft 365生産性アプリに関する記事へのリンクが含まれます。
 
7. [ユーザーをトレーニングする](/office365/admin/admin-overview/get-started-with-office-365#training-resources-for-your-users)

   ユーザーがMicrosoft 365をすばやく最大限に活用するのに役立つ短いビデオが含まれています。
 

>[!Note]
>これらの手順は、Microsoft 365 Enterpriseのカスタムデプロイから始めたい企業や[非営利団体](https://go.microsoft.com/fwlink/?LinkId=627221)向けでもあります。 
>