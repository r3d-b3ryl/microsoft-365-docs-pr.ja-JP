---
title: ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: ユーザーがモバイル デバイスからアプリや作業ファイルにアクセスする方法Office保護ポリシーについて説明します。
ms.openlocfilehash: 6e48ef857de8046854a94d470b28ba5db96b373bc8b190dc1062d4f408a9802c
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53809254"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>ユーザーによるモバイル デバイスの Office ドキュメントのアクセス方法を管理する

この記事は、このMicrosoft 365 Business Premium。

ユーザーがモバイル デバイスから Office ファイルにアクセスする方法を制御するポリシーの設定は、既定では **オフ** になっています。 セットアップ時に既定値を受け入れて、すべてのユーザーに適用される Android、iOS、および Windows 10アプリケーション ポリシーを作成することをお勧めします。 セットアップが完了したら、追加のポリシーを作成できます。 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>ユーザーがモバイル デバイスで Office ファイルにアクセスする方法を制御する設定

次の設定は、ユーザーが Office 作業ファイルにアクセスする方法を管理するために使用できます。

|Setting  <br/> |説明  <br/> |
|:-----|:-----|
|Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある  <br/> |この設定が **[オン**] の場合、ユーザーはモバイル デバイスでアプリを使用する前に、ユーザー名とパスワードに加えて、別の形式の認証Office必要があります。  <br/> |
|ログインに指定の回数失敗した場合に PIN をリセットする  <br/> |承認されていないユーザーが PIN をランダムに推測するのを防ぐため、指定した回数、エントリを間違うと、PIN がリセットされます。  <br/> |
|次の時間 Office アプリのアイドル状態が続いた場合にユーザーはもう一度サインインする必要がある  <br/> |この設定は、ユーザーが再度サインインするように求めるメッセージが表示されるまでアイドル状態にできる期間を決定します。  <br/> |
|脱獄またはルート化したデバイスでの作業ファイルへのアクセスを拒否する  <br/> |賢いユーザーは、脱獄またはルート化されたデバイスを持っている場合があります。 つまり、ユーザーはオペレーティング システムを変更できます。これにより、デバイスがマルウェアの影響を受けやすくなる可能性があります。 この設定を **オン** にすると、これらのデバイスはブロックされます。  <br/> |
|ユーザーがアプリから個人用アプリにコンテンツをコピー Office許可しない  <br/> |この設定が **[オン] の** 場合、ユーザーは作業ファイル内の情報を個人用ファイルにコピーできない。 この設定が **[オフ] の場合**、ユーザーは作業ファイルから個人アプリまたは個人アカウントに情報をコピーできます。  <br/> |
   

