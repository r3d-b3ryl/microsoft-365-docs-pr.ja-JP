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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 管理センターで一元展開を使用して、組織内のユーザーとグループにアドインを展開する方法について説明します。
ms.openlocfilehash: 4e9a3a4b7182bfd452c63abd03836623dc77260c
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138246"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>管理センターでアドインを展開する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更されました。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

Office アドインは、ドキュメントをカスタマイズしたり、Web 上の情報にアクセスする方法を効率化したりする際に役立ちます (「[Office アドインの使用を開始する](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)」を参照)。 管理者は、Microsoft 365 管理センターの集中展開機能を使用して、組織内のユーザーに対して Office アドインを展開することができます。 一元展開は、ほとんどの管理者が組織内のユーザーやグループにアドインを展開するために推奨される最も豊富な方法です。 

組織が集中展開をサポートできるかどうかを判断する方法の詳細については、「[組織でアドインの一元展開が機能](centralized-deployment-of-add-ins.md)するかどうかを判断する」を参照してください。

展開後のアドインの管理の詳細については、「管理[センターでアドインを管理](manage-addins-in-the-admin-center.md)する」を参照してください。
  
> [!NOTE]
>  Word の場合、Excel および PowerPoint では、 [Sharepoint アプリカタログ](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)を使用して、Microsoft 365 に接続していないオンプレミス環境のユーザーにアドインを展開し、必要な sharepoint アドインをサポートします。 Outlook の場合は、Exchange コントロールパネルを使用して、Microsoft 365 への接続なしでオンプレミス環境に展開します。
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Office アドインを展開する際に推奨される方法

段階的なアプローチを使用してアドインをロールアウトするには、次のことをお勧めします。
  
1. ビジネス内での利害関係者の小グループや IT 部門のメンバーを対象に、アドインをロールアウトします。 展開が成功した場合は、手順2に進みます。
    
2. 社内のその他の個人にアドインをロールアウトします。 その結果を評価し、成功した場合は完全展開のまま続行します。
    
3. すべてのユーザーに対して完全なロールアウトを実行します。
    
対象ユーザーの規模に応じて、ロールアウト手順を追加または削除できます。
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>管理センターを使用して Office アドインを展開する

作業を開始する前に、「[組織でアドインの一元展開が機能するかどうかを判断](centralized-deployment-of-add-ins.md)する」を参照してください。
  
1. 管理センターで、[**設定**] [アドイン] ページに移動し \> **Add-ins**ます。
    
2. ページの上部にある [**アドインの展開**] を選択し、[**次へ**] を選択します。
    
3. オプションを選択し、指示に従います。
  
4. Office ストアからアドインを追加するオプションを選択した場合は、アドインを選択してください。 </br>

    利用可能なアドインは、カテゴリ別に表示できます。ユーザー、**評価**、または**名前****に対して提案**されます。 Office ストアからは無料のアドインのみ利用できます。 現在、有料アドインはサポートされていません。 アドインを選択したら、使用条件に同意して続行します。 <br/> 

    > [!NOTE] 
    > Office ストアオプションでは、更新と機能拡張がユーザーに対して自動的に行われます。

5. 次のページで、**[すべてのユーザー]**、**[特定のユーザー/グループ]**、**[自分だけ]** 選択して、アドインの展開先を指定します。 検索ボックスを使用して、特定のユーザーまたはグループを検索します。 <br/>

    > [!NOTE] 
    > アドインに適用されるその他の状態については、「[アドインの状態](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)」を参照してください。
  
6. **[展開]** を選択します。
  
7. アドインを展開すると、緑色の目盛りが表示されます。 ページに記載されている手順に従って、アドインをテストします。

    > [!NOTE]
    > アプリリボンにアドインアイコンを表示するには、ユーザーが Office を再起動する必要がある場合があります。 Outlook アドインは、アプリのリボンに表示されるまでに最大24時間かかる場合があります。
    
8. 完了したら、[**次へ**] を選択します。 自分だけに展開している場合は、[他のユーザーに展開するために、**アドインへのアクセス権を持つユーザーを変更**する] を選択できます。

    組織の他のメンバーにアドインを展開した場合は、指示に従ってアドインの展開をアナウンスします。 <br/>
  
    展開されたアドインが使用可能であることをユーザーとグループに通知することをお勧めします。 アドインをいつどのように使用するかについて説明する電子メールを送信することを検討してください。 アドインに問題が発生した場合にユーザーに役立つ可能性があるヘルプコンテンツや Faq へのリンクを含めたり、追加したりすることができます。
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>ユーザーやグループにアドインを割り当てる時期を検討する

管理者は、すべてのユーザー、または特定のユーザーやグループにアドインを割り当てることができます。 各オプションには、次のような意味があります。
  
- **すべてのユーザー**このオプションを指定すると、組織内のすべてのユーザーにアドインが割り当てられます。 対象のアドインが組織全体で汎用な場合にのみ、このオプションを慎重に使用します。 
    
- **ユーザー**個々のユーザーにアドインを割り当てた後、そのアドインを新しいユーザーに展開する場合は、最初に新しいユーザーを追加する必要があります。
    
- **グループ**グループにアドインを割り当てると、そのグループに追加されたユーザーには自動的にアドインが割り当てられます。 ユーザーがグループから削除されると、そのユーザーはアドインへのアクセス権を失います。 どちらの場合も、管理者が追加の操作を行う必要はありません。 

- **自分のみ**自分だけにアドインを割り当てる場合、アドインは自分のアカウントにのみ割り当てられます。これは、アドインのテストに最適です。
    
組織に適したオプションは、構成によって異なります。 ただし、グループを使用して割り当てを行うことをお勧めします。 管理者は、グループを使用してアドインを管理し、各ユーザーを個別に割り当てる代わりに、グループのメンバーシップを制御することによって、アドインの管理が容易になります。 状況によっては、ユーザーを手動で割り当てることによって特定のユーザーに割り当てを行うことで、少数のユーザーへのアクセスを制限することが必要になる場合があります。
  
## <a name="more-about-office-add-ins-security"></a>Office アドインのセキュリティの詳細

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- データを表示する。
    
- ユーザーのドキュメントを読み取ってコンテキスト サービスを提供する。
    
- ユーザーのドキュメントのデータを読み書きして、そのユーザーに価値を提供する。
    
Office アドインの種類と機能の詳細については、「[Office アドイン プラットフォームの概要](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)」をご覧ください (特に「Office アドインの構造」セクション)。
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
アドインの更新は次のように発生します。
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

    > [!NOTE]
    > 管理者は更新を実行するために LOB アドインを削除する必要はありません。   [アドイン] セクションで、管理者は LOB アドインをクリックするだけで、右下隅の [**更新] ボタン**を選択できます。 更新プログラムは、新しいアドインのバージョンが既存のアドインのバージョンよりも大きい場合にのみ機能します。   
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 
  
## <a name="learn-more"></a>詳細情報

[管理センターでアドインを管理する](manage-addins-in-the-admin-center.md)

[Office アドインを構築](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals)する。

[未成年者とストアからのアドインの取得](minors-and-acquiring-addins-from-the-store.md)
  
[一元展開 PowerShell コマンドレットを使用してアドインを管理する](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[トラブルシューティング: ユーザーがアドインを表示していない](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
