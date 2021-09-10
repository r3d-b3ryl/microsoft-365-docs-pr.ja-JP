---
title: '[コンテンツ] ウィンドウでMicrosoft Viva ラーニング (プレビュー) の学習コンテンツ ソースを構成Microsoft 365 管理センター'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: ''
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 学習コンテンツ ソースを構成する方法については、Microsoft Viva ラーニング (プレビュー) のページでMicrosoft 365 管理センター。
ms.openlocfilehash: 977589a9b9500f062edbd962ada895436c9b2c96
ms.sourcegitcommit: 73a17ecbc06cd3e5452814637ab0484ddcdea17a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2021
ms.locfileid: "58942605"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a>[コンテンツ] ウィンドウでMicrosoft Viva ラーニング (プレビュー) の学習コンテンツ ソースを構成Microsoft 365 管理センター

> [!NOTE]
> この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。 

Microsoft 365 管理センター の管理者は、組織内の選択した個人にナレッジ管理者の役割を割り当てるかによって、ビバ ラーニング (プレビュー) に関連する設定を管理し、学習コンテンツ ソースを構成できます。

管理者は、他のラーニング コンテンツ ソース (SharePoint またはサポートされているサード パーティコンテンツ プロバイダー ソースなど) を選択して、ビバ ラーニング (Preview) のユーザーが利用できます。 次に、管理者はそれらのソースを構成して、コンテンツが検索と検出に使用可能であり、ビバ グループ (プレビュー) を使用する従業員が参照ラーニングします。

> [!NOTE]
>  ユーザーは、ブラウザーまたは埋め込みビューアーで学習ラーニング Pro Microsoft および LinkedIn 以外のユーザーにサインインします。 この構成済みの学習は、組織と第三者の間の個別のライセンス、プライバシー、およびサービス条件の対象であり、ビバ ラーニング (プレビュー) の用語には適用されません。 この種類の学習を選択する前に、組織とユーザーに契約があることを確認してください。

## <a name="assign-the-knowledge-admin-role-optional"></a>ナレッジ管理者の役割を割り当てる (オプション)

これらのタスクを実行するにはMicrosoft 365管理者である必要があります。

> [!TIP]
> 知識管理者は、適度に技術的で、SharePoint 管理者の資格情報を持っている必要があります。できれば、組織の教育、学習、トレーニング、または従業員エクスペリエンスの一部に精通しているユーザーが必要です。

### <a name="add-a-knowledge-admin"></a>ナレッジ管理者の追加

Viva ラーニング (プレビュー) のナレッジ管理者を追加するには、次の手順を実行します。

1. 左側のナビゲーションで、[ロール] Microsoft 365 管理センター移動 **します**。

2. [ロール **] ページ** の **[Azure** AD] タブで、[ナレッジ管理者] **を選択します**。
 
3. [ナレッジ管理者 **] パネルで** 、[割り当てられた管理者] **を** 選択し、[追加] を **選択します**。

     ![[ナレッジ管理者] パネルがMicrosoft 365 管理センターユーザーを追加する役割] ページが表示されます。](../media/learning/learning-add-knowledge-admin-1.png)

3. [管理者 **の追加] パネル** で、役割に選択したユーザーを選択し、[追加] を **選択します**。

     ![[管理者の追加] Microsoft 365 管理センターユーザーを追加する役割] ページが表示されます。](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a>ナレッジ管理者を削除する

Viva ラーニング (プレビュー) のナレッジ管理者を削除するには、次の手順を実行します。

1. 左側のナビゲーションで、[ロール] Microsoft 365 管理センター移動 **します**。

2. [ロール **] ページ** の **[Azure** AD] タブで、[ナレッジ管理者] **を選択します**。
 
3. [ナレッジ **管理者] パネル** の[割り当てられた管理者] タブで、[削除] を選択し、役割から削除するユーザーを選択します。 確認するには、[削除] を **選択します**。

     ![[割り当てられた管理者] Microsoft 365 管理センターユーザーを削除する役割] ページが表示されます。](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a>学習コンテンツ ソースの設定を構成する

これらのタスクを実行するにはMicrosoft 365管理者またはナレッジ管理者である必要があります。

Viva ラーニングで学習コンテンツ ソースの設定を構成するには、次の手順を実行します。

1. [組織の設定] の左側Microsoft 365 管理センター[組織の設定]**設定**  >  **移動します**。

2. [組織の **設定] ページ** の [サービス]**タブで、[** ビバ の設定] ラーニング **(プレビュー) を選択します**。

     ![設定アプリが表示Microsoft 365 管理センターページラーニング表示されます。](../media/learning/learning-sharepoint-configure1.png)

3. [ビバ **ラーニング (プレビュー)** パネルで、組織用に構成する学習コンテンツ ソースを選択し、[保存] を **選択します**。

     ![ラーニングオプションを表示するMicrosoft 365 管理センターパネルをクリックします。](../media/learning/learning-sharepoint-configure2.png)

存在するすべての学習ソースの中で、既定で有効になっているものがあります。 これらの学習ソースには、次のものが含まれます。

- LinkedIn ラーニング (無料コンテンツ)
- Microsoft Learn
- Microsoft 365トレーニング

> [!NOTE]
> LinkedIn の無料コンテンツは、LinkedIn プライバシー ポリシーとユーザー契約に基いてユーザーに提供されます。 LinkedIn は、ユーザーの IP アドレス、LinkedIn によって以前に設定された Cookie を受け取り、無料コンテンツの使用を追跡するために新しい Cookie を設定します。 ユーザーは、無料のコンテンツを受信するために LinkedIn でサインインする必要はありません。<br><br>
LinkedIn プレミアム コンテンツの場合、組織はチームがコンテンツにアクセスするサブスクリプションを必要とします。 ユーザーは LinkedIn にサインインして、その学習にアクセスする必要があります。これは、組織の用語と LinkedIn のユーザー用語の条件に従って提供されます。<br><br> Microsoft 以外のコンテンツ (無料の LinkedIn コンテンツを除く) の場合は、ユーザーが仕事用アカウントを使用してそのコンテンツにアクセスするためのサブスクリプションを組織に用意してから、ビバ ラーニング (Preview) に接続してください。 Microsoft 以外のラーニング プロバイダーに対するユーザーの個人サブスクリプションは、Viva ラーニング (Preview) と統合されません。 ユーザーは、ブラウザーまたは埋め込みビューアーで学習ラーニング Pro Microsoft および LinkedIn 以外のユーザーにサインインします。 ユーザーが組織のサブスクリプションを持つコンテンツに移動すると、個々のサブスクリプションにサインアップできるプロバイダー ページが表示される場合があります。 Microsoft 以外のすべての学習は、Microsoft 以外のプロバイダーの条項に基いて提供され、ビバ サービスの一部ラーニング。 

学習コンテンツ ソースを有効または無効にするには、ソースの横にあるチェック ボックスをオンにします。 ソースが有効になっている場合は、チェック マークが表示されます。

## <a name="third-party-content-providers"></a>サード パーティのコンテンツ プロバイダー 

利用可能な接続学習プロバイダーのセットは、いつでも変更される可能性があります。 プログラムの成長に合って、より多くのプロバイダーが参加します。 利用可能なプロバイダーは、Viva ラーニング (Preview) との接続を中止する場合もあります。

### <a name="skillsoft-as-a-content-source"></a>コンテンツ ソースとしての Skillsoft  

Viva ラーニング (プレビュー) の場合、Skillsoft を有効にし、Skillsoft コンテンツの表示を選択したユーザーは、組織の Percipio サイト名の入力を求める Percipio ページに表示されます。 ユーザーが組織のサイト名を入力すると、組織の Percipio サイトにサインインするページが表示されます。 ユーザーは、既存の資格情報を使用してサインインし、最初に選択したコンテンツを表示します。 ブラウザー キャッシュがクリアされるまで、ユーザーは Percipio サイト名の入力を 1 回だけ求めるメッセージが表示されます。 ユーザー向けこのエクスペリエンスを合理化するために、Viva ラーニング (Preview) に送信する内部通信に Percipio サイト名を含ラーニング勧めします。

これはプレビューの一時的なエクスペリエンスを目的とします。また、スキルソフトと連携してテナント固有の統合を一般提供可能にしています。これにより、ユーザーが組織の Percipio サイト名を提供する必要がある手順はバイパスされます。 

### <a name="details-on-microsoft-substrate"></a>Microsoft の基体の詳細  

Microsoft 以外のサービス (ラーニング プロバイダーまたは学習管理システム) から Viva ラーニング (Preview) にコピーするデータの場合、そのデータをビバ ラーニング (プレビュー) で直接抽出、修正、または削除することはできません。 Microsoft 以外のプロバイダーからインポートしたデータは、Microsoft 以外のソース データの変更と削除を反映するように、速やかに更新されます。

Microsoft 以外のサービスの提供者と一緒に作業し、Microsoft 以外のサービスのライセンス、サービス、またはプライバシー条件に従ってデータにアクセス、修正、削除、または抽出する必要があります。 そこで行われた変更は、Microsoft 以外のサービスとビバ ラーニング (プレビュー) のデータ更新サイクルが完了すると、ビバ ラーニング (プレビュー) で使用するために処理されたデータに反映されます。 Viva ラーニング (プレビュー) と Microsoft 以外のサービスとの間の接続をオフにした場合、そのサービスから以前にインポートしたデータはすべて削除されます。 

## <a name="next-step"></a>次の手順

[コンテンツ SharePointコンテンツ ソースとして構成する (Microsoft Viva ラーニング プレビュー)](configure-sharepoint-content-source.md)