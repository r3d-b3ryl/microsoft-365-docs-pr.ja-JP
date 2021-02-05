---
title: 管理センターでアドインを展開する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 管理センターで一元展開を使用して、組織内のユーザーとグループにアドインを展開する方法について説明します。
ms.openlocfilehash: 5d17242d98f0e58ec4bfbcfd5b7014e6a6e0a6c5
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114503"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>管理センターでアドインを展開する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。

::: moniker-end

Office アドインは、ドキュメントをカスタマイズしたり、Web 上の情報にアクセスする方法を効率化したりする際に役立ちます (「[Office アドインの使用を開始する](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)」を参照)。 管理者は、Microsoft 365 管理センターの一元展開機能を使用して、組織内のユーザーの Office アドインを展開できます。 一元展開は、ほとんどの管理者が組織内のユーザーとグループにアドインを展開する場合に推奨され、機能が豊富な方法です。 

組織で一元展開をサポートできるかどうかを判断する方法の詳細については、「アドインの一元展開が組織で機能するかどうかを判断する」を [参照してください](centralized-deployment-of-add-ins.md)。

展開後のアドインの管理の詳細については、「管理センターでアドインを管理する」 [を参照してください。](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Word の場合、Excel と PowerPoint は SharePoint アプリ カタログを使用して、Microsoft 365 への接続や [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) アドインのサポートが必要ないオンプレミス環境のユーザーにアドインを展開します。 Outlook では、Exchange コントロール パネルを使用して、Microsoft 365 に接続せずにオンプレミス環境に展開します。
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Office アドインを展開する際に推奨される方法

段階的なアプローチを使用してアドインをロールアウトするには、次の方法をお勧めします。
  
1. ビジネス内での利害関係者の小グループや IT 部門のメンバーを対象に、アドインをロールアウトします。 展開が成功した場合は、手順 2 に進みます。
    
2. ビジネス内のより多くの個人にアドインを展開します。 再度、結果を評価し、成功した場合は完全展開を続行します。
    
3. すべてのユーザーに対して完全なロールアウトを実行します。
    
対象ユーザーのサイズに応じて、ロールアウト手順を追加または削除できます。
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>管理センターを使用して Office アドインを展開する

開始する前に、「アドインの一元展開が組織で機能するかどうかを判断する」 [を参照してください](centralized-deployment-of-add-ins.md)。
  
1. 管理センターで、[設定アドイン] \> **ページに移動** します。 [アドイン] ページが表示 **されな場合** は、[統合アプリアドインの設定] \>  \> **ページに移動** します。
    
2. ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を選択 **します**。
 
    > [!NOTE]
    > 管理センターは、統合アプリの展開エクスペリエンスに更新されています。 If you don't see the above steps, go to Centralized Deployment section by going to **Settings**  >  **Integrated apps**. [統合アプリ] **ページの上部で** 、[アドイン] **を選択します**。
    
3. オプションを選択し、指示に従います。
  
4. Office ストアからアドインを追加するオプションを選択した場合は、アドインを選択します。 </br>

    利用可能なアドインは、カテゴリ (推奨、評価、名前)**で表示****できます**。 無料のアドインのみをストアからOfficeできます。 現在、有料アドインはサポートされていません。 アドインを選択した後、続行する使用条件に同意します。 <br/> 

    > [!NOTE] 
    > [ストアOfficeオプションを使用すると、更新プログラムと拡張機能がユーザーに自動的に展開されます。

5. 次のページで、**[すべてのユーザー]**、**[特定のユーザー/グループ]**、**[自分だけ]** 選択して、アドインの展開先を指定します。 検索ボックスを使用して、特定のユーザーまたはグループを検索します。 <br/>

    > [!NOTE] 
    > アドインに適用される他の状態については、「アドインの状態」 [を参照してください](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)。
  
6. **[展開]** を選択します。
  
7. アドインを展開すると、緑色の目盛りが表示されます。 ページ上の指示に従ってアドインをテストします。

    > [!NOTE]
    > ユーザーは、アプリ のリボンOfficeアイコンを表示するために、アプリを再起動する必要がある場合があります。 Outlook アドインがアプリ リボンに表示されるのに最大 24 時間かかる場合があります。
    
8. 完了したら、[次へ] を **選択します**。 自分専用に展開した場合は、[アドインにアクセスできるユーザーを変更する] を選択して、より多くのユーザーに展開できます。

    組織の他のメンバーにアドインを展開した場合は、指示に従ってアドインの展開をアナウンスします。 <br/>
  
    展開されたアドインが使用可能なユーザーとグループに通知する方法をお試しください。 アドインを使用する場合と方法を説明する電子メールを送信する場合を検討します。 ユーザーがアドインに問題がある場合に役立つ可能性があるヘルプ コンテンツや FAQ を含めるか、リンクします。
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>ユーザーやグループにアドインを割り当てる時期を検討する

管理者は、すべてのユーザー、または特定のユーザーやグループにアドインを割り当てることができます。 各オプションには、次のような意味があります。
  
- **すべてのユーザー** このオプションは、組織内のすべてのユーザーにアドインを割り当てる場合に使用します。 対象のアドインが組織全体で汎用な場合にのみ、このオプションを慎重に使用します。 
    
- **ユーザー** アドインを個々のユーザーに割り当て、そのアドインを新しいユーザーに展開する場合は、最初に新しいユーザーを追加する必要があります。
    
- **グループ** グループにアドインを割り当てると、グループに追加されたユーザーにアドインが自動的に割り当てられます。 ユーザーがグループから削除されると、そのユーザーはアドインへのアクセス権を失います。 どちらの場合も、管理者から追加の操作は必要ありません。 

- **Just me** 自分にだけアドインを割り当てる場合、アドインは自分のアカウントにのみ割り当てられます。これは、アドインのテストに最適です。
    
組織に適切なオプションは、構成によって異なります。 ただし、グループを使用して割り当てを作成することをお勧めします。 管理者は、グループを使用してそれらのグループのメンバーシップを制御することで、アドインを管理する方が、個別のユーザーを割り当てるのではなく、その度に簡単に管理できる場合があります。 場合によっては、ユーザーを手動で割り当て、特定のユーザーに割り当て、小さなユーザー セットへのアクセスを制限する必要があります。
  
## <a name="more-about-office-add-ins-security"></a>アドインOfficeの詳細

Office アドインに結合されている XML マニフェスト ファイルは、アドインに関する一部のメタデータを含んでいますが、最も重要なのは、すべてのコードとロジックを含む Web アプリケーションを参照していることです。アドインにはさまざまな機能があります。たとえば、アドインでは次のことができます。
  
- データを表示する。
    
- ユーザーのドキュメントを読み取ってコンテキスト サービスを提供する。
    
- ユーザーのドキュメントのデータを読み書きして、そのユーザーに価値を提供する。
    
Office アドインの種類と機能の詳細については、「[Office アドイン プラットフォームの概要](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)」をご覧ください (特に「Office アドインの構造」セクション)。
  
ユーザーのドキュメントを操作するため、アドインはマニフェストで必要なアクセス許可を宣言する必要があります。5 レベルの JavaScript API アクセス許可モデルが、タスク ウィンドウ アドインのユーザーにプライバシーとセキュリティの基礎を提供します。Office ストア 内のアドインの多くは ReadWriteDocument レベルで、ほとんどすべてのアドインは少なくとも ReadDocument レベルをサポートします。アクセス許可レベルの詳細については、「[コンテンツとタスク ウィンドウ アドインでの API 使用のアクセス許可の要求](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)」をご覧ください。
  
マニフェストを更新するとき、一般的に変更されるのはアドインのアイコンとテキストです。場合によっては、アドイン コマンドが変更されます。ただし、アドインのアクセス許可は変更されません。アドインのすべてのコードとロジックが実行される Web アプリケーションは、Web アプリケーションの性質上、いつでも変更される可能性があります。
  
アドインの更新は次のように発生します。
  
- **基幹業務アドイン:** この場合は、管理者が明示的にマニフェストをアップロードすると、アドインは管理者がメタデータの変更をサポートする新しいマニフェスト ファイルをアップロードすることを要求します。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。 

    > [!NOTE]
    > 管理者は、更新を実行するために LOB アドインを削除する必要があります。   [アドイン] セクションで、管理者は LOB アドインをクリックするだけで、右下隅にある[更新] ボタンを選択できます。 更新は、新しいアドインのバージョンが既存のアドインのバージョンより大きい場合にのみ機能します。   
    
- **Office ストア アドイン:** 管理者が Office ストア からアドインを選択した場合、アドインが Office ストア で更新されると、そのアドインは後で一元展開で更新されます。次に関連する Office アプリケーションが起動すると、アドインが更新されます。Web アプリケーションはいつでも変更できます。 
  
## <a name="learn-more"></a>詳細情報

[管理センターでアドインを管理する](manage-addins-in-the-admin-center.md)

[最初の Word 作業ウィンドウ アドインをビルドします](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)。

[マイナーとストアからアドインを取得する](minors-and-acquiring-addins-from-the-store.md)
  
[一元展開 PowerShell コマンドレットを使用してアドインを管理する](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[トラブルシューティング: ユーザーにアドインが表示されない](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
