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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: 管理者がネイティブ コネクタをセットアップして使用して、Twitter データをユーザーにインポートする方法Microsoft 365。
ms.openlocfilehash: ff29ebf19f292a2d052c7172f31779ca48cae428
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201915"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Twitter データをアーカイブするコネクタをセットアップする (プレビュー)

データをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターのコネクタを使用して、Twitter からユーザーにMicrosoft 365。 コネクタをセットアップして構成した後、組織の Twitter アカウントに (スケジュールに基づいて) 接続し、アイテムのコンテンツを電子メール メッセージ形式に変換し、Microsoft 365 のメールボックスにそれらのアイテムをインポートします。

Twitter データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能を Twitter データに適用できます。 たとえば、メールボックスが訴訟ホールドに置かれたり、保持ポリシーに割り当てられたりすると、Twitter データは保持されます。 コンテンツ検索を使用してサード パーティのデータを検索するか、Twitter データが保存されているメールボックスを管理者に関連付Advanced eDiscoveryできます。 コネクタを使用して Twitter データをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

Twitter データをインポートした後、訴訟ホールド、コンテンツ検索、In-Place アーカイブ、監査、通信コンプライアンス、Microsoft 365 保持ポリシーなどの Microsoft 365 コンプライアンス機能をメールボックスに格納されているデータに適用できます。 たとえば、コンテンツ検索を使用して Twitter データを検索したり、データが保管担当者に保存されているメールボックスを特定のケースに関連付Advanced eDiscoveryできます。 コネクタを使用して Twitter データをインポートおよびアーカイブMicrosoft 365、組織が政府および規制ポリシーに準拠しつ付けるのに役立ちます。

## <a name="before-you-set-up-a-connector"></a>コネクタをセットアップする前に

組織の Twitter アカウントからデータをインポートおよびアーカイブするには、Microsoft 365 コンプライアンス センターコネクタをセットアップして構成する前に、次の前提条件を満たしてください。

- 組織の Twitter アカウントが必要です。コネクタのセットアップ時に、このアカウントにサインインする必要があります。

- 組織に有効な Azure サブスクリプションが必要です。 既存の Azure サブスクリプションがない場合は、次のいずれかのオプションにサインアップできます。

    - [無料の 1 年間 Azure サブスクリプションにサインアップする](https://azure.microsoft.com/free) 

    - [Pay-As-Go Azure サブスクリプションにサインアップする](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > サブスクリプション[にAzure Active Directory](use-your-free-azure-ad-subscription-in-office-365.md)されている無料のサブスクリプションは、Microsoft 365のコネクタをサポートMicrosoft 365 コンプライアンス センター。

- Twitter コネクタは、1 日に合計 200,000 アイテムをインポートできます。 1 日に 200,000 件を超える Twitter アイテムがある場合、それらのアイテムはいずれも 1 日にインポートMicrosoft 365。

- (手順 5) の Microsoft 365 コンプライアンス センター手順 5 で Twitter コネクタをセットアップするユーザーには、Exchange Online でメールボックスインポートエクスポートの役割を割り当てる必要Exchange Online。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 [メールボックスのインポートエクスポート] 役割は、組織の [組織の管理] 役割グループに追加Exchange Online。 または、役割グループを作成し、メールボックスインポートエクスポートの役割を割り当て、適切なユーザーをメンバーとして追加できます。 詳細については、「グループ内の[役割グループを](/Exchange/permissions-exo/role-groups#create-role-groups)管理[](/Exchange/permissions-exo/role-groups#modify-role-groups)する」の「役割グループの作成」または「役割グループの変更」セクションを参照Exchange Online。

## <a name="step-1-create-an-app-in-azure-active-directory"></a>手順 1: アプリをアプリで作成Azure Active Directory

最初の手順は、新しいアプリをアプリ (AAD) Azure Active Directory登録します。 このアプリは、Twitter コネクタの手順 2 で実装する Web アプリ リソースに対応します。

手順については、「アプリを作成する[」](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)を参照Azure Active Directory。

この手順が完了すると (手順の手順に従って)、次の情報をテキスト ファイルに保存します。 これらの値は、展開プロセスの後の手順で使用されます。

- AAD アプリケーション ID

- AAD アプリケーション シークレット

- テナント ID

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>手順 2: コネクタ Web サービスを azure GitHubリポジトリから Azure アカウントに展開する

次の手順では、Twitter API を使用して Twitter アカウントに接続し、データを抽出する Twitter コネクタ アプリのソース コードを展開し、データを Microsoft 365 にインポートします。 組織に展開する Twitter コネクタは、組織の Twitter アカウントからこの手順で作成Azure Storage場所にアイテムをアップロードします。 Microsoft 365 コンプライアンス センター (手順 5) で Twitter コネクタを作成すると、Microsoft 365 インポート サービスは Azure Storage の場所から Microsoft 365 のメールボックスに Twitter データをコピーします。 前の「コネクタをセットアップ[する](#before-you-set-up-a-connector)前に」セクションで説明したように、有効な Azure Storage Azure サブスクリプションを持っている必要があります。

Twitter コネクタ アプリのソース コードを展開するには、次の方法を実行します。

1. このサイト[に移動GitHubします](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)。

2. [Azure **に展開する] をクリックします**。

詳細な手順については、「コネクタ Web サービスを Azure アカウントに展開する」を参照GitHub[を参照してください](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)。

手順に従ってこの手順を完了する場合は、次の情報を提供します。

- APISecretKey: この手順の完了時に、このシークレットを作成します。 手順 5 で使用します。

- tenantId: 手順 1 で Twitter アプリMicrosoft 365作成した後にコピーした組織のテナント ID Azure Active Directory ID です。

この手順を完了した後、必ずアプリのサービス URL (たとえば) をコピーしてください `https://twitterconnector.azurewebsites.net` 。 この URL を使用して、手順 3、手順 4、および手順 5) を完了する必要があります。

## <a name="step-3-create-developer-app-on-twitter"></a>手順 3: Twitter で開発者アプリを作成する

次の手順では、Twitter で開発者アプリを作成して構成します。 手順 7 で作成するカスタム コネクタは、Twitter アプリを使用して Twitter API を操作し、組織の Twitter アカウントからデータを取得します。

手順については [、「Create the Twitter app」を参照してください](deploy-twitter-connector.md#step-3-create-the-twitter-app)。

この手順の完了時 (手順に従って)、次の情報をテキスト ファイルに保存します。 これらの値は、手順 4 で Twitter コネクタ アプリを構成するために使用されます。

- Twitter API キー

- Twitter API シークレット キー

- Twitter アクセス トークン

- Twitter アクセス トークン シークレット

## <a name="step-4-configure-the-twitter-connector-app"></a>手順 4: Twitter コネクタ アプリを構成する

次の手順では、手順 2 で展開した Twitter コネクタ アプリに構成設定を追加します。 これを行うには、コネクタ アプリのホーム ページに移動して構成します。

手順については、「コネクタ Web アプリの [構成」を参照してください](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)。

この手順の完了時 (手順に従って)、次の情報 (前の手順を完了した後にテキスト ファイルにコピーした情報) を提供します。

- Twitter API キー (手順 3 で取得)

- Twitter API シークレット キー (手順 3 で取得)

- Twitter アクセス トークン (手順 3 で取得)

- Twitter Access Token Secret (手順 3 で取得)

- Azure Active Directory ID (手順 1 で取得した AAD アプリケーション ID)

- Azure Active Directory アプリケーション シークレット (手順 1 で取得した AAD アプリケーション シークレット)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>手順 5: アプリケーションで Twitter コネクタをセットアップMicrosoft 365 コンプライアンス センター

最後の手順は、組織の Twitter アカウントから、Microsoft 365 コンプライアンス センター で指定されたメールボックスにデータをインポートする Twitter コネクタを Microsoft 365。 この手順を完了すると、Microsoft 365インポート サービスは組織の Twitter アカウントからデータのインポートを開始Microsoft 365。

詳細な手順については、「Twitter コネクタをセットアップする」を参照[Microsoft 365 コンプライアンス センター。](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center) 

この手順の完了時 (手順の手順に従って)、次の情報 (手順を完了した後にテキスト ファイルにコピーした情報) を提供します。

- Azure アプリ サービスの URL (手順 2 で取得、たとえば `https://twitterconnector.azurewebsites.net` )

- APISecretKey (手順 2 で作成した)