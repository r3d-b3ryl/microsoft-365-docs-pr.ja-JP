---
title: Microsoft 365 管理センターで Microsoft Viva Learning (プレビュー) の学習コンテンツ ソースを構成する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 05/12/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Microsoft 365 管理センターで Microsoft Viva Learning (プレビュー) の学習コンテンツ ソースを構成する方法について説明します。
ms.openlocfilehash: aba5c9f4eae3de5a1dfccd306bd38b2e3eeea5d0
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333544"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで Microsoft Viva Learning (プレビュー) の学習コンテンツ ソースを構成する

> [!NOTE]
> この記事の情報は、商用リリース前に大幅に変更される可能性があるプレビュー製品に関連しています。 

Microsoft 365 管理センターの管理者は、組織内の選択した個人にナレッジ管理者の役割を割り当てるかによって、ビバ ラーニング (プレビュー) に関連する設定を管理し、学習コンテンツ ソースを構成できます。

管理者は、他の学習コンテンツ ソース (SharePoint やサポートされているサード パーティコンテンツ プロバイダーソースなど) を選択します。ビバ ラーニング (プレビュー) のユーザーが利用できます。 その後、管理者はそれらのソースを構成して、コンテンツが検索と検出に使用可能であり、ビバ ラーニング (Preview) を使用する従業員が閲覧できるよう構成します。

> [!NOTE]
>  ユーザーは、ブラウザーまたは埋め込みビューアーで Microsoft および LinkedIn Learning Pro 以外の学習にサインインします。 この構成済みの学習は、組織と第三者の間の個別のライセンス、プライバシー、およびサービス条項の対象であり、ビバ ラーニング (プレビュー) の用語には適用されません。 この種類の学習を選択する前に、組織とユーザーに契約があることを確認してください。

## <a name="assign-the-knowledge-admin-role-optional"></a>ナレッジ管理者の役割を割り当てる (オプション)

これらのタスクを実行するには、Microsoft 365 グローバル管理者である必要があります。

> [!TIP]
> ナレッジ管理者は、適度に技術的で、既存の SharePoint 管理者資格情報を持っている必要があります。できれば、組織の教育、学習、トレーニング、または従業員エクスペリエンスの一部に精通しているユーザーが必要です。

### <a name="add-a-knowledge-admin"></a>ナレッジ管理者の追加

ビバ ラーニング (プレビュー) のナレッジ管理者を追加するには、次の手順を実行します。

1.  Microsoft 365 管理センターの左側のナビゲーションで、[ロール] に **移動します**。

2.  [ロール **] ページ** の **[Azure** AD] タブで、[ナレッジ管理者] **を選択します**。
 
3.  [ナレッジ管理者 **] パネルで** 、[割り当てられた管理者] **を** 選択し、[追加] を **選択します**。

     ![ユーザーを追加する [ナレッジ管理者] パネルを表示する Microsoft 365 管理センターの [役割] ページ。](../media/learning/learning-add-knowledge-admin-1.png)

3.  [管理者 **の追加] パネル** で、役割に選択したユーザーを選択し、[追加] を **選択します**。

     ![[管理者の追加] パネルを表示する Microsoft 365 管理センターの [役割] ページで、ユーザーを追加します。](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a>ナレッジ管理者を削除する

Viva Learning (プレビュー) のナレッジ管理者を削除するには、次の手順を実行します。

1.  Microsoft 365 管理センターの左側のナビゲーションで、[ロール] に **移動します**。

2.  [ロール **] ページ** の **[Azure** AD] タブで、[ナレッジ管理者] **を選択します**。
 
3.  [ナレッジ **管理者] パネル** の[割り当てられた管理者] タブで、[削除] を選択し、役割から削除するユーザーを選択します。 確認するには、[削除] を **選択します**。

     ![ユーザーを削除する [割り当てられた管理者] パネルを表示する Microsoft 365 管理センターの [役割] ページ。](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a>学習コンテンツ ソースの設定を構成する

これらのタスクを実行するには、Microsoft 365 グローバル管理者またはナレッジ管理者である必要があります。

Viva Learning で学習コンテンツ ソースの設定を構成するには、次の手順を実行します。

1.  Microsoft 365 管理センターの左側のナビゲーションで、[設定] [組織の設定]  >  **に移動します**。

2.  [組織の **設定] ページ** の [サービス] **タブで** 、[ビバ ラーニング **(プレビュー) ] を選択します**。

     ![一覧表示されているラーニング アプリを示す Microsoft 365 管理センターの [設定] ページ。](../media/learning/learning-sharepoint-configure1.png)

3.  [ビバ **ラーニング (プレビュー)]** パネルで、組織用に構成する学習コンテンツ ソースを選択し、[保存] を **選択します**。

     ![コンテンツ ソースオプションを表示する Microsoft 365 管理センターの学習パネル。](../media/learning/learning-sharepoint-configure2.png)

存在するすべての学習ソースの中で、既定で有効になっているものがあります。 これらの学習ソースには、次のものが含まれます。

- LinkedIn Learning (無料コンテンツ)
- Microsoft Learn
- Microsoft 365 トレーニング

> [!NOTE]
> LinkedIn の無料コンテンツは、LinkedIn プライバシー ポリシーとユーザー契約に基いてユーザーに提供されます。 LinkedIn は、ユーザーの IP アドレス、LinkedIn によって以前に設定された Cookie を受け取り、無料コンテンツの使用を追跡するために新しい Cookie を設定します。 ユーザーは、無料のコンテンツを受信するために LinkedIn でサインインする必要はありません。<br><br>
LinkedIn プレミアム コンテンツの場合、組織はチームがコンテンツにアクセスするサブスクリプションを必要とします。 ユーザーは LinkedIn にサインインして、その学習にアクセスする必要があります。これは、組織の用語と LinkedIn のユーザー用語の条件に従って提供されます。<br><br> Microsoft 以外のコンテンツ (無料の LinkedIn コンテンツを除く) の場合は、ビバ ラーニング (プレビュー) に接続する前に、ユーザーが仕事用アカウントを使用してそのコンテンツにアクセスするためのサブスクリプションを組織に用意してください。 Microsoft 以外のラーニング プロバイダーに対するユーザーの個人サブスクリプションは、ビバ ラーニング (プレビュー) と統合されません。 ユーザーは、ブラウザーまたは埋め込みビューアーで Microsoft および LinkedIn Learning Pro 以外の学習にサインインします。 ユーザーが組織のサブスクリプションを持つコンテンツに移動すると、個々のサブスクリプションにサインアップできるプロバイダー ページが表示される場合があります。 Microsoft 以外のすべての学習は、ビバ ラーニングの一部としてではなく、Microsoft 以外のプロバイダーの条件に基いて提供されます。 

学習コンテンツ ソースを有効または無効にするには、ソースの横にあるチェック ボックスをオンにします。 ソースが有効になっている場合は、チェック マークが表示されます。

## <a name="third-party-content-providers"></a>サード パーティのコンテンツ プロバイダー 

利用可能な接続学習プロバイダーのセットは、いつでも変更される可能性があります。 プログラムの成長に合って、より多くのプロバイダーが参加します。 利用可能なプロバイダーは、ビバ ラーニング (プレビュー) との接続を中止する場合もあります。

### <a name="skillsoft-as-a-content-source"></a>コンテンツ ソースとしての Skillsoft  

ビバ ラーニング (プレビュー) では、Skillsoft を有効にし、Skillsoft コンテンツの表示を選択したユーザーは、組織の Percipio サイト名の入力を求める Percipio ページに表示されます。 ユーザーが組織のサイト名を入力すると、組織の Percipio サイトにサインインするページが表示されます。 ユーザーは、既存の資格情報を使用してサインインし、最初に選択したコンテンツを表示します。 ブラウザー キャッシュがクリアされるまで、ユーザーは Percipio サイト名の入力を 1 回だけ求めるメッセージが表示されます。 ユーザーのこのエクスペリエンスを合理化するには、Viva Learning (Preview) に関して送信する内部コミュニケーションに Percipio サイト名を含めすることをお勧めします。

これはプレビューの一時的なエクスペリエンスを目的とします。また、スキルソフトと連携してテナント固有の統合を一般提供可能にしています。これにより、ユーザーが組織の Percipio サイト名を提供する必要がある手順はバイパスされます。 

### <a name="details-on-microsoft-substrate"></a>Microsoft の基体の詳細  

Microsoft 以外のサービス (ラーニング プロバイダーまたは学習管理システム) から Viva Learning (Preview) にコピーするデータの場合、そのデータを直接抽出、修正、または削除することはできません。ビバ ラーニング (Preview) でデータを削除することはできません。 Microsoft 以外のプロバイダーからインポートしたデータは、Microsoft 以外のソース データの変更と削除を反映するように、速やかに更新されます。

Microsoft 以外のサービスの提供者と一緒に作業し、Microsoft 以外のサービスのライセンス、サービス、またはプライバシー条件に従ってデータにアクセス、修正、削除、または抽出する必要があります。 そこで行われた変更は、Microsoft 以外のサービスとビバ ラーニング (プレビュー) のデータ更新サイクルが完了すると、ビバ ラーニング (プレビュー) で使用するために処理されたデータに反映されます。 Viva Learning (Preview) と Microsoft 以外のサービス間の接続をオフにした場合、そのサービスから以前にインポートしたデータはすべて削除されます。 

## <a name="next-step"></a>次の手順

[SharePoint を Microsoft Viva Learning の学習コンテンツ ソースとして構成する (プレビュー)](configure-sharepoint-content-source.md)