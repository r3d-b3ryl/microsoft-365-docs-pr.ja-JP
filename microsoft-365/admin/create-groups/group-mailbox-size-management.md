---
title: Microsoft 365 グループ メールボックス サイズ管理
description: Microsoft 365 のグループ メールボックス サイズ管理について説明します。
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: ''
ms.reviewer: ''
author: serdars
ms.author: serdars
ms.openlocfilehash: e97ed8b6f7d4d57fe993c6039b165f1a8e85eeb8
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67277240"
---
# <a name="microsoft-365-group-mailbox-size-management"></a>Microsoft 365 グループ メールボックス サイズ管理 

各 Microsoft 365 グループには、グループで受信したメールを格納する専用メールボックスが用意されています。 グループ メールボックスは、SharePoint Online、Yammer、Teams などのアプリケーションでも使用されます。グループ メールボックスには、50 GB の初期ストレージ クォータが備わっています。 グループ メールボックスのクォータに達すると、電子メールがグループ NDR に送信されます。 そのため、グループ メールボックスがクォータに達しないように、古いコンテンツをグループ メールボックスから削除することをお勧めします。 

次の方法は、クォータの計算のしくみ、ベスト プラクティス、またはグループ メールボックスがそのクォータに達しないようにするためのプロアクティブなアプローチを理解するのに役立ちます。 また、グループ メールボックスがクォータに達した場合、またはクォータを超えた場合に実行されるアクションの経過。

## <a name="proactive-approach-to-keep-group-mailbox-size-in-check"></a>グループメールボックスのサイズをチェックしたままにするプロアクティブなアプローチ 

アイテム保持ポリシーを作成して、指定した制限時間に達すると、グループからの古いメールが自動的に削除されるようにすることができます。 詳細については、Microsoft 365 グループのアイテム保持ポリシーを作成する手順については、「 [アイテム保持ポリシーの作成と構成](/microsoft-365/compliance/create-retention-policies)」を参照してください。 アイテム保持ポリシーでは、データをクリーンアップするために作業サイクルが長くなるので、グループ メールボックスの作成中に適用する必要があります。 アイテム保持ポリシーは、グループ メールボックスからデータをすぐにフラッシュまたは削除するためのツールとして使用することはできません。

## <a name="to-monitor-the-group-mailbox-size"></a>グループメールボックスのサイズを監視するには: 

次のコマンドを使用して、グループ メールボックスに割り当てられている現在のクォータを確認します。

```PowerShell
Get-Mailbox -GroupMailbox <groupname> |ft ProhibitSendReceiveQuota,ProhibitSendQuota,IssueWarningQuota 
```

次のコマンドを使用して、グループ メールボックスの現在のサイズを確認します。

```PowerShell
Get-MailboxStatistics <groupname> | ft TotalDeletedItemSize,TotalItemSize 
```

## <a name="steps-to-follow-when-the-group-mailbox-has-reached-its-limit"></a>グループ メールボックスが制限に達したときに従う手順:  

前述のように、グループ メールボックスは、さまざまなアプリケーションでデータを格納するために使用されます。 グループ メールボックスがクォータに達したら、より多くのデータを占有するフォルダーを特定し、適切なアクションを実行することが重要です。 

1. 次のコマンドから始めて、グループ メールボックスのクォータが超過したことを確認します。 

   ```PowerShell
   Get-MailboxStatistics <groupname> |ft TotalItemSize,TotalDeletedItemSize 
   ```

   グループ メールボックスは、さまざまな `TargetQuota`システム、回復可能、およびユーザーに配布されます。 "User" に一致する `TargetQuota` フォルダーは、グループ クォータの計算で考慮される唯一のフォルダーです。  

2. 次のコマンドを使用して、ユーザー データを占有しているフォルダー サイズを確認します。 

   ```PowerShell
   Get-MailboxFolderStatistics <groupname> | where { $_.TargetQuota -like 'User' } | ft Name,FolderPath,FolderType,FolderSize 

   Get-MailboxFolderStatistics <groupname> -FolderScope NonIPMRoot | where { $_.TargetQuota -like 'User' } | ft Name,FolderType,*size* 
   ```
3. フォルダーのクォータまたはサイズを確認します。

4. 「Connector Web パーツを使用する」で説明されているように、領域[を使用するフォルダーが](https://support.microsoft.com/en-us/office/use-the-connector-web-part-db0756aa-f78f-4b74-8b19-be5dca0420e1?ns=spostandard&version=16&syslcid=1033&uilcid=1033&appver=spo160&helpid=wssenduser_useconnectorwebpart_fl862286&ui=en-us&rs=en-us&ad=us)`SharePointWebPartsConnectorMessages`次の場合は、次の操作を行います。

   1. 使用しない場合は、コネクタを無効にします。 

   2. メッセージが既定でクリアされるまで 90 日間待ちます。 

5. グループ メールボックス サイズを占有する特別なフォルダーがない場合は、 [グループ メールボックスのアイテム保持ポリシーを適用し、アイテム保持ポリシー](/microsoft-365/compliance/create-retention-policies) がグループ メールボックスから電子メールをクリーンアップするのを待ちます。 
  

