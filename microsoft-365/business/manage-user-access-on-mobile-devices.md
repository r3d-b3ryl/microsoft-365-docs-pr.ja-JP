---
title: ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: モバイル デバイスからの Office アプリケーションをセキュリティで保護されたアクセスが役立つ保護ポリシーについて説明します。
ms.openlocfilehash: 75dbe79acccabd851c43259a165e79bfe3c509c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869314"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する

 ユーザーがモバイル デバイスから Office ファイルにアクセスする方法を制御するポリシーの設定は、既定では **オフ**になっています。セットアップ時に既定値を受け入れて、すべてのユーザーに適用される、Android、iOS、Windows 10 のアプリケーション ポリシーを作成することをお勧めします。セットアップが完了したら、追加のポリシーを作成できます。 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>ユーザーがモバイル デバイスで Office ファイルにアクセスする方法を制御する設定

次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。
  
|||
|:-----|:-----|
|設定  <br/> |説明  <br/> |
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  <br/> |この設定を **オン**にすると、ユーザーは、ユーザー名とパスワードの他に、別の認証フォームを提供しないと、モバイル デバイスで Office アプリを使用できません。  <br/> |
|ログインに指定の回数失敗した場合に PIN をリセットする  <br/> |承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。  <br/> |
|次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある  <br/> |この設定は、もう一度サインインを求められるまで、どのくらいユーザーをアイドル状態にできるかを指定します。  <br/> |
|脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する  <br/> |賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。これは、ユーザーがオペレーティング システムを変更できるため、デバイスがマルウェアの危険にさらされる可能性が高くなることを意味します。この設定を **オン**にすると、これらのデバイスはブロックされます。  <br/> |
|Office アプリのコンテンツを個人のアプリにコピーすることをユーザーに許可する  <br/> |これは既定で許可していますが、設定を **オン**にすると、ユーザーは作業ファイル内の情報を個人のファイルにコピーできます。この設定を **オフ**にした場合、ユーザーは作業ファイルから個人用アプリまたは個人のアカウントに情報をコピーすることはできません。  <br/> |
   

