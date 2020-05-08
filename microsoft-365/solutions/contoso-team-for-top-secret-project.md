---
title: Contoso Corporation のトップシークレットプロジェクトの分離されたチーム
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: Ent_Architecture
description: '概要: Contoso 社がトップシークレットプロジェクトのセキュリティ分離を備えたチームを使用して、新しいスイートの製品とサービスを開発する方法について説明します。'
ms.openlocfilehash: 1083c9d3db3be9ca528b2eee40f072aa17c7431e
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159457"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso Corporation のトップシークレットプロジェクトの分離されたチーム

上級管理職がオフサイトになると、Contoso 社の CEO は、今後5年間で Contoso 社の利益を2倍にすることができる新しいスイートの製品とサービスの開発を命じました。 ビジネス、エンジニアリング、マーケットプランを開発する最上位のプロジェクトは、 **Project 2x**という名前で、会社全体にわたる主なスタッフは recruited でした。 

研究開発のタイムラインは厳しいものでした。つまり、共同作業を効率的に行い、セキュリティで保護された会議、継続的な会話、ファイルストレージを提供する必要がありました。

プロジェクト2X の結果として得られる成果物は、ビジネスプラン、製品とエンジニアリングの仕様、およびマーケティング資料とスケジュールが、Word、Excel、および PowerPoint のファイルの形式で表示されます。 

機密情報のため、これらのファイルへのアクセスは次のようになりました。

- プロジェクト2チームメンバーに制限されます。
- セキュリティで保護されたフォルダーの外部でファイルが配布された場合でも、Project 2X のチームメンバーにのみアクセスを許可するためのアクセス許可で暗号化および保護されます。

Contoso IT スタッフは、Project 2X の[セキュリティ分離を備えたチーム](secure-teams-security-isolation.md)を使用して、これらの手順を実行していました。

## <a name="step-1-created-a-private-team"></a>手順 1: プライベートチームを作成する

最初に、チームの基礎となる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が[推奨する sharepoint アクセスポリシー](../enterprise/sharepoint-file-access-policies.md)を構成しました。

次に Contoso IT 管理者は、Project 2X という名前の新しいプライベートチームを作成し、Project 2X スタッフのユーザーアカウントをメンバーとして追加しました。

構成の詳細については、「 [Create a private team](secure-teams-security-isolation.md#create-a-private-team)」を参照してください。

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>手順 2: Project 2X チームの機密ラベルを作成しました

Contoso admins は、 **Project 2x**という名前の新しい機密ラベルを作成しました。次のようになります。

- 暗号化が必要です。
- Project 2 の Microsoft 365 グループに対して共同編集権限を許可します。

基になる Project 2X SharePoint サイトの [**ドキュメント**] セクションにあるファイルは、次の方法で保護されています。

- サイトのアクセス許可。これは、Project 2X Microsoft 365 グループのメンバーにのみアクセスを許可します。
- プロジェクトがサイトから移動またはコピーされた場合に、ファイルと共に送信される、暗号化とアクセス許可を持つ2つのプロジェクトの機密ラベル。

構成の詳細については、「 [Create a 機密ラベル](secure-teams-security-isolation.md#create-a-sensitivity-label)」を参照してください。

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>手順 3: 基になる SharePoint サイトを構成する

最初に、チームの基礎となる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が[推奨する sharepoint アクセスポリシー](../enterprise/sharepoint-file-access-policies.md)を構成しました。

次に、プロジェクト2X がサイトへのアクセスを共有しないようにするために、サイトの追加のアクセス許可設定を構成しました。 構成の詳細については、「 [SharePoint の設定 (セキュリティの分離を使用したチーム向け](secure-teams-security-isolation.md#sharepoint-settings))」を参照してください。

プロジェクト2チームの最終的な構成を次に示します。

![プロジェクト2チームの最終的な構成](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>手順 4: トレーニングを受けた Project 2X チームメンバー

Contoso のセキュリティスタッフは、次の手順に従ってステップ実行する必須のコースで、Project 2X のチームメンバーをトレーニングしています。

- 新しい Project 2X teams にアクセスする方法、会議とチャットを使用する方法、およびチームファイルで共同作業する方法について説明します。
- チーム内で新しいファイルを作成し、ローカルに作成された新しいファイルをアップロードする方法について説明します。
- DLP ポリシーによって、ファイルが外部で共有されることをブロックする方法のデモ。
- Project 2X 機密ラベルを使用してファイルにラベルを付ける方法について説明します。
- プロジェクトの2つのラベルがチームを離れたときでもファイルを保護する方法についてのデモ。

最終的には、セキュリティで保護された環境で、Project 2X のチームメンバーがチャット、会議、およびファイルのセキュリティで保護された環境で共同作業を行うことができました。

以下は、プロジェクト2x 機密ラベルが割り当てられた、基になる Project 2X サイトに保存されているファイルの例です。

![基になる Project 2X サイトに保存されているファイルの例](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

いくつかのインスタンスでは、Project 2X のチームメンバーは、オフライン作業のために Project 2X ラベルで保護されたファイルをローカルドライブにダウンロードしていました。 ただし、資格情報を開くときに資格情報の入力を求められた後で、それらの間違いを認識して削除しました。

Teams のグループ作業環境と Microsoft 365 のセキュリティ機能により、project 2X の詳細はプロジェクトの期間中に機密情報として保持されていました。 Contoso 社はプランを発表し、新しい製品とサービスを顧客や投資家の成功および競合他社の chagrin に展開する過程にあります。

## <a name="next-step"></a>次の手順

組織内で[セキュリティの分離を使用してチームを展開](secure-teams-security-isolation.md)します。

