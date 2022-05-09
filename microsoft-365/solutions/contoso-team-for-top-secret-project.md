---
title: Contoso Corporation の極秘プロジェクトの分離されたチーム
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: '概要: Contoso は、最高機密プロジェクトのセキュリティ分離を備えたチームを使用して、製品とサービスの新しいスイートを開発しました。'
ms.openlocfilehash: 5b6bc72a6476301cf3239aeb7f68486f15ebbac8
ms.sourcegitcommit: 22cae7ec541268d519d45518c32f22bf5811aec1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62523927"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Contoso Corporation の極秘プロジェクトの分離されたチーム

経営幹部のオフサイトの後、Contoso の CEO は、今後 5 年間で Contoso の利益を 2 倍にできる製品とサービスの新しいスイートの開発を命じた。 ビジネス、エンジニアリング、および市場計画を開発するための最も秘密のプロジェクトは **、2X Project** 命名され、会社全体の主要スタッフが採用されました。 

研究と開発のタイムラインは厳しく、コラボレーションを効率的に行い、安全な会議、継続的な会話、ファイル ストレージを提供する必要がありました。

Project 2X の成果物は、Word、Excel、およびPowerPoint ファイル形式のビジネス プラン、製品とエンジニアリングの仕様、マーケティング資料とスケジュールでした。 

機密性の高い性質上、これらのファイルへのアクセスは次のとおりです。

- Project 2X チーム メンバーとシニア リーダーシップに制限されています。
- セキュリティで保護されたフォルダーの外部にファイルが配布された場合でも、Project 2X チーム メンバーとシニア リーダーシップへのアクセスのみを許可するアクセス許可で暗号化され、保護されます。

Contoso IT スタッフは、Project 2X とこれらの手順のために[セキュリティ分離を備えたチーム](secure-teams-security-isolation.md)を使用しました。

## <a name="step-1-created-a-private-team"></a>手順 1: プライベート チームを作成する

まず、チームの基になるSharePoint サイトへのアクセスを保護するために、Contoso IT 管理者は[推奨されるSharePoint アクセス ポリシー](../security/office-365-security/sharepoint-file-access-policies.md)を構成しました。

次に、Contoso IT 管理者が 2X Projectという名前の新しいプライベート チームを作成し、Project 2X スタッフのユーザー アカウントをメンバーとして追加しました。 また、2 倍のチーム所有者のみがプライベート チャネルProject作成できるようにチームを構成しました。

構成の詳細については、「 [プライベート チームの作成](secure-teams-security-isolation.md#create-a-private-team)」を参照してください。

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>手順 2: Project 2X チームの秘密度ラベルを作成しました

Contoso 管理者は、**Project 2X** という名前の新しい秘密度ラベルを作成しました。

- 暗号化を有効にしました。
- Project 2X Microsoft 365 グループに対する許可Co-Authorアクセス許可。
- シニア リーダーシップ グループに対して許可されたビューアーのアクセス許可。
- 管理されていないデバイスへのアクセスをブロックしました。

基になる Project 2X SharePoint サイトの **[ドキュメント]** セクションのファイルは、次の方法で保護されました。

- サイトのアクセス許可。これは、Project 2X Microsoft 365 グループのメンバーに対してのみフル アクセス許可を許可し、シニア リーダーシップ グループに対する読み取りアクセス許可を許可します。
- Project 2X 秘密度ラベル。ファイルがサイトから移動またはコピーされた場合にファイルと共に移動する暗号化とアクセス許可。

構成の詳細については、「 [秘密度ラベルの作成](secure-teams-security-isolation.md#create-a-sensitivity-label)」を参照してください。

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>手順 3: 基になるSharePoint サイトを構成する

まず、チームの基になるSharePoint サイトへのアクセスを保護するために、Contoso IT 管理者は[推奨されるSharePoint アクセス ポリシー](../security/office-365-security/sharepoint-file-access-policies.md)を構成しました。

次に、サイトの追加のアクセス許可設定を構成しました。

- Project 2X グループ メンバーがサイトへのアクセスを共有できないようにする。 構成の詳細については、[セキュリティ分離を備えたチームのSharePoint設定に関する説明を](secure-teams-security-isolation.md#sharepoint-settings)参照してください。
- シニア リーダーシップ グループの読み取りアクセス許可。

次に、Project 2X グループ メンバーがサイトへのアクセスを共有できないように、サイトの追加のアクセス許可設定を構成しました。 

Project 2X のプライベート チャネルが作成されると、グループ所有者はゲスト共有を無効にし、既定の共有リンクを **[特定のユーザー**] の値に設定しました。

セキュリティ分離を使用して、Project 2X チームの結果として得られる構成を次に示します。

![Project 2X チームの結果の構成。](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>手順 4: トレーニング済みProject 2X チーム メンバー

Contoso セキュリティ スタッフは、次の手順を踏んだ必須コースで、Project 2X チーム メンバーをトレーニングしました。

- 新しいProject 2X チームにアクセスする方法、会議とチャットを使用する方法、およびチーム ファイルで共同作業する方法。
- チームで新しいファイルを作成し、ローカルで作成された新しいファイルをアップロードする方法。
- Project 2X 秘密度ラベルを使用してファイルにラベルを付ける方法。
- Project 2X ラベルがチームから離れた場合でもファイルを保護する方法のデモンストレーション。

最終的な結果は、Project 2X チーム メンバーがチャット、会議、ファイル用のセキュリティで保護された環境で共同作業を行うセキュリティで保護された環境でした。

Project 2X 秘密度ラベルが割り当てられた、基になるProject 2X サイトに格納されているファイルの例を次に示します。

![基になるProject 2X サイトに格納されているファイルの例。](../media/contoso-team-for-top-secret-project-example.png)

いくつかのインスタンスで、Project 2X チーム メンバーは、オフライン作業のためにProject 2X ラベルで保護されたファイルをローカル ドライブにダウンロードしました。 

ただし、資格情報を開くときに資格情報の入力を求められた後、間違いを認識して削除しました。

Teamsのコラボレーション環境とMicrosoft 365のセキュリティ機能により、Project 2X の詳細はプロジェクトの期間中は秘密にされていました。 Contoso は計画を発表し、顧客と投資家の喜びと競合他社のチャグリンに新しい製品とサービスを展開中です。

## <a name="next-step"></a>次の手順

組織[にセキュリティ分離を持つチームをデプロイ](secure-teams-security-isolation.md)します。

