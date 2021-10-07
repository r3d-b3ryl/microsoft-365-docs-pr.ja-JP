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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: '概要: Contoso 社は、トップシークレット プロジェクトのセキュリティ分離を持つチームを使用して、新しい製品とサービスのスイートを開発する方法について説明します。'
ms.openlocfilehash: c789e74bc54183f16f7de7801ecc77b76f4913f6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191279"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso Corporation のトップシークレット プロジェクトの分離チーム

エグゼクティブ オフサイトの後、Contoso の CEO は、次の 5 年間で Contoso の利益を倍増できる新しい製品とサービスの開発を命じた。 ビジネス、エンジニアリング、および市場計画を開発するトップ シークレット プロジェクトは、Project **2X** に指名され、会社全体の主要なスタッフが採用されました。 

研究開発のスケジュールは厳しく、共同作業を効率的に行い、安全な会議、継続的な会話、ファイルストレージを提供する必要があります。

Project 2X の成果物は、ビジネス プラン、製品とエンジニアリングの仕様、および Word、Excel、および PowerPoint ファイルの形式のマーケティング資料とスケジュールでした。 

機密性の高い性質のため、これらのファイルへのアクセスは次の条件に従います。

- 2X チーム Projectおよびシニア リーダーシップに制限されています。
- セキュリティで保護されたフォルダーの外部にファイルが配布された場合でも、Project 2X チーム メンバーとシニア リーダーシップにのみアクセスできるアクセス許可を持つ暗号化と保護。

Contoso IT スタッフ[](secure-teams-security-isolation.md)は、2X およびこれらの手順に対してセキュリティProjectチームを使用しました。

## <a name="step-1-created-a-private-team"></a>手順 1: プライベート チームを作成する

まず、チームの基になるサイトSharePointを保護するために、Contoso IT 管理者が推奨されるアクセス ポリシーを構成SharePoint[しました](../security/office-365-security/sharepoint-file-access-policies.md)。

次に、Contoso IT 管理者が Project 2X という名前の新しいプライベート チームを作成し、Project 2X スタッフのユーザー アカウントをメンバーとして追加しました。 また、2X チームの所有者だけがプライベート チャネルProject作成できるよう、チームを構成しました。

構成の詳細については、「プライベート チームの [作成」を参照してください](secure-teams-security-isolation.md#create-a-private-team)。

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>手順 2: 2X チームに対してProjectラベルを作成する

Contoso 管理者は 2X という名前の新しい **Projectを作成** しました。

- 暗号化を有効にします。
- 2X Co-Authorグループのアクセス許可Project許可Microsoft 365されます。
- シニア リーダーシップ グループに対して許可された閲覧者のアクセス許可。
- 管理されていないデバイスへのアクセスがブロックされました。

基になる **2X** サイトの [ドキュメント] セクションProjectはSharePointで保護されています。

- このサイトのアクセス許可は、Project 2X Microsoft 365 グループのメンバーにのみフル アクセス許可を許可し、シニア リーダーシップ グループに対する読み取りアクセス許可を許可します。
- このProject 2X の感度ラベルで、ファイルを移動またはサイトからコピーした場合にファイルと一緒に移動する暗号化とアクセス許可を指定します。

構成の詳細については、「感度ラベルを作成 [する」を参照してください](secure-teams-security-isolation.md#create-a-sensitivity-label)。

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>手順 3: 基になるサイトを構成SharePointする

まず、チームの基になるサイトSharePointを保護するために、Contoso IT 管理者が推奨されるアクセス ポリシーを構成SharePoint[しました](../security/office-365-security/sharepoint-file-access-policies.md)。

次に、サイトの追加のアクセス許可設定を構成しました。

- 2X グループ Projectメンバーがサイトへのアクセスを共有しに行かねない場合。 構成の詳細については、「セキュリティ分離[SharePointチームの設定」を参照してください](secure-teams-security-isolation.md#sharepoint-settings)。
- シニア リーダーシップ グループの読み取りアクセス許可。

次に、2X グループ メンバーがサイトへのアクセスを共有Projectを防ぐために、サイトの追加のアクセス許可設定を構成しました。 

2X のプライベート チャネルProject、グループ所有者はゲスト共有を無効にし、既定の共有リンクを [特定のユーザー]**の値に設定** します。

セキュリティを分離した 2X チームProject構成を次に示します。

![2X チームの結果Project構成。](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>手順 4: トレーニングProject 2X チーム メンバー

Contoso のセキュリティ スタッフは、Project 2X チーム メンバーのトレーニングを必須コースで行いました。

- 2X チームの新しいProjectにアクセスする方法、会議とチャットを使用する方法、およびチーム ファイルで共同作業する方法。
- チーム内に新しいファイルを作成し、ローカルで作成された新しいファイルをアップロードする方法。
- 2X の感度ラベルを使用Projectラベルを付ける方法。
- チームから離れる場合Project 2X ラベルがファイルを保護する方法のデモンストレーション。

その結果、2X チーム のメンバー Project、チャット、会議、ファイルの安全な環境で共同作業を行う安全な環境が得られます。

次に、基になる 2X サイトに保存されているファイルのProject 2X のProjectを示します。

![基になる 2X サイトに格納されているファイルProject例です。](../media/contoso-team-for-top-secret-project-example.png)

いくつかのインスタンスでは、Project 2X チーム メンバーは、Project 2X ラベルで保護されたファイルをローカル ドライブにダウンロードしてオフライン作業を行いました。 

ただし、資格情報を開く際に資格情報の入力を求めるメッセージが表示された後、間違いを気付いて削除しました。

Teams のコラボレーション環境と Microsoft 365 のセキュリティ機能のため、Project 2X の詳細はプロジェクトの間秘密に保たれ続けた。 Contoso 社は計画を発表し、顧客と投資家の喜びと競合他社のチャグリンに新しい製品とサービスを展開中です。

## <a name="next-step"></a>次の手順

[組織にセキュリティの分離を持つ](secure-teams-security-isolation.md) チームを展開します。

