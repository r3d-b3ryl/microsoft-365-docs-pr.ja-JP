---
title: ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: ユーザーがモバイルデバイスから Office アプリや作業ファイルにアクセスする方法を管理できる保護ポリシーについて説明します。
ms.openlocfilehash: 21e83114664d06aaeb27b08d9f4e2153eea02030
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550319"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する

 ユーザーがモバイル デバイスから Office ファイルにアクセスする方法を制御するポリシーの設定は、既定では **オフ**になっています。 すべてのユーザーに適用される Android、iOS、Windows 10 のアプリケーションポリシーを作成するには、セットアップ時に既定値を受け入れることをお勧めします。 セットアップが完了したら、追加のポリシーを作成できます。 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>ユーザーがモバイル デバイスで Office ファイルにアクセスする方法を制御する設定

次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。
  
|||
|:-----|:-----|
|設定  <br/> |説明  <br/> |
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  <br/> |この設定が**オンになって**いる場合は、ユーザーのモバイルデバイスで Office アプリを使用できるようにするために、ユーザー名とパスワードに加えて、別の形式の認証を提供する必要があります。  <br/> |
|ログインに指定の回数失敗した場合に PIN をリセットする  <br/> |承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。  <br/> |
|次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある  <br/> |この設定により、ユーザーがもう一度サインインするように求めるメッセージが表示されるまでの待機時間を指定できます。  <br/> |
|脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する  <br/> |賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。 これは、ユーザーがオペレーティングシステムを変更できるため、デバイスがマルウェアに対してより脆弱になる可能性があることを意味します。 この設定を **オン**にすると、これらのデバイスはブロックされます。  <br/> |
|ユーザーが Office アプリから個人用アプリにコンテンツをコピーすることを許可しない  <br/> |この設定が**オン**の場合、ユーザーは作業ファイル内の情報を個人用ファイルにコピーすることはできません。 この設定が**オフ**の場合、ユーザーは作業ファイルから個人のアプリまたは個人のアカウントに情報をコピーできます。  <br/> |
   

