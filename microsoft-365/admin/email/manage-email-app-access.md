---
title: Microsoft 365 管理センターでメール アプリへのアクセスを管理する
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkEXCHANGE
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
ms.assetid: d00b6b83-1f14-4e9c-a2c5-dbd9a92816f4
ROBOTS: NOINDEX, NOFOLLOW
description: ユーザーが電子メール、予定表、連絡先にアクセスするために使用できるモバイル アプリを選択する方法について説明します。
ms.openlocfilehash: 5f5a96a0ac44757cfe168db87deb494019759c36
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64780239"
---
# <a name="manage-email-app-access-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでメール アプリへのアクセスを管理する

モバイル メール アクセス設定を使用して、組織内のユーザーが職場または学校のアカウントにアクセスして電子メール、予定表、連絡先にアクセスするために使用できるモバイル アプリを選択します。
  
> [!IMPORTANT]
> Microsoft Intuneを使用しているか、Exchange<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">管理センター</a>でモバイル デバイス管理設定を構成していない限り、組織はこの設定にアクセスできます。
  
## <a name="manage-email-app-options"></a>電子メール アプリのオプションを管理する

> [!IMPORTANT]
> この機能を使用しない場合、ユーザーのエクスペリエンスに変更はありません。 モバイル メール アプリを使用して、モバイル デバイスからメール、予定表、連絡先の職場または学校アカウントにアクセスできます。

1. 管理センターで、 [**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">サービス&amp;アドイン</a>] ページの順に移動します。

2. [ **モバイル メール アクセス オプション** ] ページで、チェック ボックスをオンにし、組織内のユーザーが自分のデバイスで電子メール アプリを使用する方法を選択します。
  
組織内のユーザーが自分のモバイル デバイスから職場または学校のアカウントにアクセスする方法を設定するオプションを選択します
  
- **Outlookのみ**- 組織内のユーザーは、モバイル デバイスで Android 用のOutlookまたは iOS アプリ用のOutlookを使用する必要があります。

- **すべての電子メール アプリ** - 組織内のすべてのユーザーにOutlookの使用を求められますが、任意の電子メール アプリの使用を選択できます。

- **組織内の** 新しいユーザーまたはデバイスに対して、Outlookの使用を求めるメッセージが表示されますが、電子メール アプリの使用は選択できます。

詳細については、 [モバイル デバイスから電子メールにアクセスするためのオプション](access-email-from-a-mobile-device.md)を確認してください。
  
## <a name="new-user-or-device-is-activated-in-your-organization"></a>組織内で新しいユーザーまたはデバイスがアクティブ化される

組織内のユーザーが職場または学校のメールをサードパーティの電子メール アプリまたは新しいデバイスに追加するとすぐに、 **組織に代わって Microsoft** から電子メールが届きます。 メールでは、Outlookモバイル アプリを使用する利点について知らせ、ダウンロード場所へのリンクを提供します。 その後、ユーザーは、サード パーティ製アプリを引き続き使用するか、Outlookモバイル アプリを使用するかを選択できます。 ユーザーがこの電子メールを最初に受信してから 24 時間以内に、デバイスは検疫に入り、電子メール、予定表、連絡先データは更新されません。 Outlookモバイル アプリを使用することを選択した場合、サード パーティアプリは検疫されたままになり、データはOutlookモバイル アプリとのみ同期されます。 サード パーティ製アプリの使用を継続することにした場合、データは即座に同期を開始します。 最初の 24 時間にアクションが実行されない場合、メールは受信トレイから削除され、データはサーバーから自動的に同期され始めます。
  
## <a name="previously-configured-users-in-your-organization"></a>組織内で以前に構成されたユーザー

組織内のすべてのユーザーにOutlookを推奨する場合は、新しいユーザーに対して上記のエクスペリエンスに加えて、以前に職場または学校のメール アカウントをサード パーティのアプリに接続したユーザーは、この設定が有効になってから 48 時間以内 **に組織に代わって Microsoft** から電子メールを受け取ります。 メールでは、Outlookモバイル アプリを使用する利点について知らせ、ダウンロード場所へのリンクを提供します。 その後、ユーザーは、サード パーティ製アプリを引き続き使用するか、Outlookモバイル アプリを使用するかを選択できます。 ユーザーがこの電子メールを最初に受信してから 24 時間以内に、デバイスは検疫に入り、電子メール、予定表、連絡先データは更新されません。 Outlookモバイル アプリを使用することを選択した場合、サード パーティアプリは検疫されたままになり、データはOutlookモバイル アプリとのみ同期されます。 サード パーティ製アプリの使用を継続することにした場合、データは即座に同期を開始します。 最初の 24 時間にアクションが実行されない場合、メールは受信トレイから削除され、データはサーバーから自動的に同期され始めます。
