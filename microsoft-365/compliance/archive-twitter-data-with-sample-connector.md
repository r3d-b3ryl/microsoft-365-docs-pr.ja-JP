---
title: コネクタセットアップしてTwitter のデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 管理者がネイティブ コネクタをセットアップして使用して Twitter データを Microsoft 365 にインポートする方法について説明します。
ms.openlocfilehash: 5b35259985664ac47b9d1f6265c8ca4282a4cd31
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790065"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>コネクタを設定して Twitter データをアーカイブする (プレビュー)

Microsoft 365 コンプライアンス センターのコネクタを使用して、Twitter から Microsoft 365 にデータをインポートしてアーカイブします。 コネクタを設定して構成した後、組織の Twitter アカウントに (スケジュールに基づいて) 接続し、アイテムのコンテンツを電子メール メッセージ形式に変換し、それらのアイテムを Microsoft 365 のメールボックスにインポートします。

Twitter データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を Twitter データに適用できます。 たとえば、メールボックスが訴訟ホールドの対象にされた場合、またはアイテム保持ポリシーに割り当てられた場合、Twitter データは保持されます。 コンテンツ検索を使用してサード パーティのデータを検索したり、Twitter データが保存されているメールボックスを Advanced eDiscovery ケースの保管担当者に関連付けできます。 コネクタを使用して Microsoft 365 で Twitter データをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

Twitter データをインポートした後、メールボックスに保存されているデータに、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 アイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を適用できます。 たとえば、コンテンツ検索を使用して Twitter データを検索したり、Advanced eDiscovery ケースでデータが保管されているメールボックスを保管担当者に関連付けできます。 コネクタを使用して Microsoft 365 で Twitter データをインポートおよびアーカイブすると、組織が政府や規制のポリシーに準拠しつながっているのに役立ちます。

## <a name="before-you-set-up-a-connector"></a>コネクタを設定する前に

Microsoft 365 コンプライアンス センターでコネクタをセットアップして構成し、組織の Twitter アカウントからデータをインポートおよびアーカイブする前に、次の前提条件を満たします。

- 組織用の Twitter アカウントが必要です。コネクタを設定するときに、このアカウントにサインインする必要があります。

- 組織には有効な Azure サブスクリプションが必要です。 既存の Azure サブスクリプションがない場合は、次のいずれかのオプションにサインアップできます。

    - [1 年間無料の Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free) 

    - [Pay-As-You-Go Azure サブスクリプションにサインアップする](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Microsoft 365 サブスクリプションに含まれている無料の [Azure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md) サブスクリプションは、セキュリティ/コンプライアンス センターのコネクタ&サポートしていません。

- Twitter コネクタは、1 日に合計 200,000 アイテムをインポートできます。 1 日に 200,000 を超える Twitter アイテムがある場合、それらのアイテムは Microsoft 365 にインポートされません。

- Microsoft 365 コンプライアンス センター (手順 5 で) で Twitter コネクタをセットアップするユーザーには、Exchange Online の "Mailbox Import Export/メールボックスのインポートエクスポート" 役割が割り当てられている必要があります。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 "Mailbox Import Export/メールボックスのインポートとエクスポート" 役割は、Exchange Online の "Organization Management/組織の管理" 役割グループに追加できます。 または、役割グループを作成し、Mailbox Import Export 役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「Exchange Online[で役割](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups)グループ[](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)を管理する」の「役割グループの作成」または「役割グループの変更」セクションを参照してください。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: Azure Active Directory でアプリを作成する

最初の手順では、Azure Active Directory (AAD) に新しいアプリを登録します。 このアプリは、Twitter コネクタの手順 2 で実装する Web アプリ リソースに対応しています。

詳しい手順については、「Azure Active Directory でアプリを作成 [する」を参照してください](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)。

この手順が完了すると (詳しい手順に従って)、次の情報をテキスト ファイルに保存します。 これらの値は、展開プロセスの後の手順で使用されます。

- AAD アプリケーション ID

- AAD アプリケーション シークレット

- テナント ID

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>手順 2: コネクタ Web サービスを GitHub リポジトリから Azure アカウントに展開する

次の手順では、Twitter API を使用して Twitter アカウントに接続し、データを抽出して Microsoft 365 にインポートする Twitter コネクタ アプリのソース コードを展開します。 組織に展開する Twitter コネクタは、組織の Twitter アカウントから、この手順で作成された Azure Storage の場所にアイテムをアップロードします。 Microsoft 365 コンプライアンス センター (手順 5 で) で Twitter コネクタを作成すると、Microsoft 365 インポート サービスは Azure Storage の場所から Microsoft 365 のメールボックスに Twitter データをコピーします。 「コネクタをセットアップする [前](#before-you-set-up-a-connector) に」セクションで説明したように、Azure ストレージ アカウントを作成するには、有効な Azure サブスクリプションが必要です。

Twitter コネクタ アプリのソース コードを展開するには、

1. この [GitHub サイトに移動します](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)。

2. [Azure **に展開] をクリックします**。

詳しい手順については、「GitHub から Azure アカウントにコネクタ Web サービスを展開 [する」を参照してください](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

ステップ バイ ステップの手順に従ってこの手順を完了する場合は、次の情報を提供します。

- APISecretKey: この手順の完了時にこのシークレットを作成します。 手順 5 で使用します。

- tenantId: 手順 1 で Azure Active Directory で Twitter アプリを作成した後にコピーした Microsoft 365 組織のテナント ID。

この手順を完了した後、必ずアプリのサービス URL (たとえば) をコピーします `https://twitterconnector.azurewebsites.net` 。 この URL を使用して、手順 3、手順 4、および手順 5 を完了する必要があります。

## <a name="step-3-create-developer-app-on-twitter"></a>手順 3: Twitter で開発者アプリを作成する

次の手順では、Twitter で開発者アプリを作成して構成します。 手順 7 で作成したカスタム コネクタは、Twitter アプリを使用して Twitter API と対話し、組織の Twitter アカウントからデータを取得します。

詳しい手順については、「Twitter アプリの作成 [」を参照してください](deploy-twitter-connector.md#step-3-create-the-twitter-app)。

この手順が完了すると (詳しい手順に従って)、次の情報をテキスト ファイルに保存します。 これらの値は、手順 4 で Twitter コネクタ アプリを構成するために使用されます。

- Twitter API キー

- Twitter API の秘密キー

- Twitter アクセス トークン

- Twitter アクセス トークン シークレット

## <a name="step-4-configure-the-twitter-connector-app"></a>手順 4: Twitter コネクタ アプリを構成する

次の手順では、手順 2 で展開した Twitter コネクタ アプリに構成設定を追加します。 これを行うには、コネクタ アプリのホーム ページに移動して構成します。

詳しい手順については、「コネクタ Web アプリを構成 [する」を参照してください](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)。

この手順の完了時に (詳しい手順に従って) 次の情報を入力します (前の手順を完了した後にテキスト ファイルにコピーした情報)。

- Twitter API キー (手順 3 で取得)

- Twitter API 秘密キー (手順 3 で取得)

- Twitter アクセス トークン (手順 3 で取得)

- Twitter アクセス トークン シークレット (手順 3 で取得)

- Azure Active Directory アプリケーション ID (手順 1 で取得した AAD アプリケーション ID)

- Azure Active Directory アプリケーション シークレット (手順 1 で取得した AAD アプリケーション シークレット)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>手順 5: Microsoft 365 コンプライアンス センターで Twitter コネクタをセットアップする

最後の手順では、組織の Twitter アカウントから Microsoft 365 の指定されたメールボックスにデータをインポートする Microsoft 365 コンプライアンス センターで Twitter コネクタを設定します。 この手順を完了すると、Microsoft 365 インポート サービスは組織の Twitter アカウントから Microsoft 365 へのデータのインポートを開始します。

詳しい手順については [、「Microsoft 365](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center)コンプライアンス センターで Twitter コネクタをセットアップする」を参照してください。 

この手順の完了時に (詳しい手順に従って) 次の情報を入力します (手順を完了した後にテキスト ファイルにコピーした情報)。

- Azure アプリ サービスの URL (手順 2 で取得(例 `https://twitterconnector.azurewebsites.net` : )

- APISecretKey (手順 2 で作成したキー)
