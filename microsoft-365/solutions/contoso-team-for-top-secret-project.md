---
title: Contoso Corporation のトップシークレット プロジェクトの分離チーム
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: '概要: Contoso 社は、トップシークレット プロジェクトのセキュリティ分離を持つチームを使用して、新しい製品とサービスのスイートを開発する方法について説明します。'
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029018"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso Corporation のトップシークレット プロジェクトの分離チーム

エグゼクティブ オフサイトの後、Contoso の CEO は、次の 5 年間で Contoso の利益を倍増できる新しい製品とサービスの開発を命じた。 ビジネス、エンジニアリング、および市場計画を開発するトップ シークレット プロジェクトは **Project 2X** と名付け、会社全体の主要なスタッフが採用されました。 

研究開発のスケジュールは厳しく、共同作業を効率的に行い、安全な会議、継続的な会話、ファイルストレージを提供する必要があります。

Project 2X の成果物は、ビジネス プラン、製品およびエンジニアリング仕様、および Word、Excel、および PowerPoint ファイルの形式でのマーケティング資料とスケジュールでした。 

機密性の高い性質のため、これらのファイルへのアクセスは次の条件に従います。

- Project 2X チーム メンバーとシニア リーダーシップに制限されています。
- ファイルがセキュリティで保護されたフォルダーの外部に配布されている場合でも、Project 2X チーム メンバーとシニア リーダーシップへのアクセスのみを許可するアクセス許可を持つ暗号化と保護。

Contoso IT スタッフ[](secure-teams-security-isolation.md)は、Project 2X とこれらの手順にセキュリティ分離を持つチームを使用しました。

## <a name="step-1-created-a-private-team"></a>手順 1: プライベート チームを作成する

まず、チームの基になる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が推奨される SharePoint アクセス ポリシー [を構成しました](../security/office-365-security/sharepoint-file-access-policies.md)。

次に、Contoso IT 管理者が Project 2X という名前の新しいプライベート チームを作成し、Project 2X スタッフのユーザー アカウントをメンバーとして追加しました。 また、Project 2X チームの所有者だけがプライベート チャネルを作成できるようチームを構成しました。

構成の詳細については、「プライベート チームの [作成」を参照してください](secure-teams-security-isolation.md#create-a-private-team)。

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>手順 2: Project 2X チームの感度ラベルを作成する

Contoso 管理者は、Project 2X という名前の新しい **感度ラベルを作成** しました。

- 暗号化を有効にします。
- Project 2X Co-Author 365 グループのアクセス許可を許可します。
- シニア リーダーシップ グループに対して許可された閲覧者のアクセス許可。
- 管理されていないデバイスへのアクセスがブロックされました。

基になる **Project** 2X SharePoint サイトの [ドキュメント] セクションのファイルは、次の方法で保護されています。

- Project 2X Microsoft 365 グループのメンバーに対する完全なアクセス許可とシニア リーダーシップ グループへの読み取りアクセス許可のみを許可するサイトのアクセス許可。
- サイトから移動またはコピーされた場合にファイルと一緒に移動する暗号化とアクセス許可を含む Project 2X の感度ラベル。

構成の詳細については、「感度ラベルを作成 [する」を参照してください](secure-teams-security-isolation.md#create-a-sensitivity-label)。

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>手順 3: 基になる SharePoint サイトを構成する

まず、チームの基になる SharePoint サイトへのアクセスを保護するために、Contoso IT 管理者が推奨される SharePoint アクセス ポリシー [を構成しました](../security/office-365-security/sharepoint-file-access-policies.md)。

次に、サイトの追加のアクセス許可設定を構成しました。

- Project 2X グループ メンバーがサイトへのアクセスを共有しなけれな 構成の詳細については、「 [セキュリティ分離を使用するチームの SharePoint 設定」を参照してください](secure-teams-security-isolation.md#sharepoint-settings)。
- シニア リーダーシップ グループの読み取りアクセス許可。

次に、Project 2X グループ メンバーがサイトへのアクセスを共有しなかぐために、サイトの追加のアクセス許可設定を構成しました。 

Project 2X のプライベート チャネルが作成されると、グループ所有者はゲスト共有を無効にし、既定の共有リンクを [特定のユーザー] **の値に設定** します。

セキュリティを分離した Project 2X チームの構成を次に示します。

![Project 2X チームの結果の構成](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>手順 4: トレーニング済みの Project 2X チーム メンバー

Contoso のセキュリティ スタッフは、Project 2X チーム メンバーを必須コースでトレーニングし、次のステップを踏み出しました。

- 新しい Project 2X チームにアクセスする方法、会議とチャットを使用する方法、およびチーム ファイルで共同作業する方法。
- チーム内に新しいファイルを作成し、ローカルで作成された新しいファイルをアップロードする方法。
- Project 2X の感度ラベルを使用してファイルにラベルを付ける方法。
- Project 2X ラベルがチームを離れる場合でもファイルを保護する方法のデモンストレーション。

最後の結果は、Project 2X チーム メンバーがチャット、会議、ファイルの安全な環境で共同作業を行う安全な環境でした。

Project 2X の感度ラベルが割り当てられている基になる Project 2X サイトに保存されているファイルの例を次に示します。

![基になる Project 2X サイトに格納されているファイルの例](../media/contoso-team-for-top-secret-project-example.png)

いくつかのインスタンスで、Project 2X チーム メンバーは、Project 2X ラベルで保護されたファイルをローカル ドライブにダウンロードしてオフライン作業を行いました。 

ただし、資格情報を開く際に資格情報の入力を求めるメッセージが表示された後、間違いを気付いて削除しました。

Teams のコラボレーション環境と Microsoft 365 のセキュリティ機能のため、Project 2X の詳細はプロジェクト期間中秘密に保たれ続けでした。 Contoso 社は計画を発表し、顧客と投資家の喜びと競合他社のチャグリンに新しい製品とサービスを展開中です。

## <a name="next-step"></a>次の手順

[組織にセキュリティの分離を持つ](secure-teams-security-isolation.md) チームを展開します。

