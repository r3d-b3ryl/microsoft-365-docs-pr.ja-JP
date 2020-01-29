---
title: Office 365、O365 提出、Office 365 スパムの問題、O365 誤検出、office 365 での送信フィッシング、office 365 での電子メールの送信、メールの送信、メールをスキャン、フィッシングに関する Microsoft scan を使用している、microsoft scan for スパム、送信電子メール、電子メールの送信、dodgy メール、誤ったアクターメール、疑わしい、信頼できないメール、レポートフィッシング電子メール、microsoft への電子メールの報告、詐欺メールを microsoft に報告する、microsoft への電子メールの報告、microsoft への電子メールの報告、スパム受信トレイ内のメール office 365、電子メール office のウイルス365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 疑わしいメール、疑わしいフィッシングメール、スパム、およびその他の潜在的に有害なメッセージ、Url、およびその他の潜在的な問題のあるメールを、Office 365 テナントから Microsoft にスキャンするために提出する方法について説明します。
ms.openlocfilehash: c46017becfed546557fbf59c0dbbe12e9af53aa0
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "41573034"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a>フィッシングの疑いのあるスパム、、Url、およびファイルを Microsoft for Office 365 スキャンに提出する方法

管理者は、Microsoft が Office 365 でスキャンするファイルまたはネットワークメッセージ ID、Url、ファイルを使用して、メールを送信できます。
更新された提出物セクションには、ユーザーが報告したメッセージと、EOP を使用しているすべてのお客様が利用できます。

電子メールを送信すると、受信メールがテナントに許可されている可能性のあるポリシーや、メール内のすべての Url と添付ファイルの調査に関する情報が得られます。 メールが許可されているポリシーには、個々のユーザーの信頼できる差出人のリストと、Exchange メールフロールール (トランスポートルールとも呼ばれる) などのテナントレベルのポリシーが含まれます。

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>Office 365 スキャンに対して疑わしいコンテンツを Microsoft に送信する方法

Microsoft にコンテンツを送信するには、送信ページの左上にある [**新しい送信**] ボタンをクリックします。 ページの右側にあるポップアップが表示され、電子メール、URL、またはファイルのいずれかを送信するオプションが表示されます。

### <a name="submit-a-questionable-email-to-microsoft"></a>疑わしいメールを Microsoft に送信する

![電子メール送信の例](../media/submission-flyout-email.PNG)

1. 電子メールを送信するには、[**電子**メール] を選択し、電子メール**ネットワークのメッセージ ID**を指定するか、電子メールファイルをアップロードします。

2. ポリシーチェックの実行対象となる受信者を指定します。 ポリシーチェックは、ユーザーまたはテナントレベルのポリシーによって、電子メールがスキャンをバイパスしたかどうかを判断します。

3. 電子メールがブロックされているかどうかを指定します。 メールがブロックされている必要がある場合は、スパム、フィッシング、またはマルウェアとしてブロックされているかどうかを指定します。 可能な種類がわからない場合は、最適な judgement を使用してください。

   - 送信時のポリシーによってフィルターがバイパスされた場合は、そのポリシーに関する情報が表示されます。

   - 1つまたは複数のポリシーによってフィルターがバイパスされていない場合、スキャンは数分で完了します。 [状態] リンクをクリックすると、送信に関する追加情報が表示されます。 これには、ポリシーチェックの結果と rescan verdict が含まれます。 メモこれにより、Office 365 ATP の完全なフィルター処理スタックからメールが再度実行されることはありませんが、メール、URL、またはファイルの特定の属性に基づいて、部分的な再スキャンが実行されます。

4. [**送信**] ボタンをクリックします。

### <a name="send-a-suspect-url-to-microsoft"></a>疑わしい URL を Microsoft に送信する

![電子メール送信の例](../media/submission-url-flyout.png)

1. URL を送信するには、ポップアップから [ **url** ] を選択します。 プロトコル (**https://**) を含む完全な URL を入力します。

   [**フィルター済み**] を選択した場合は、URL がフィッシングまたはマルウェアであるかどうかを指定します。

2. [**送信**] ボタンをクリックします。

### <a name="submit-a-suspected-file-to-microsoft"></a>疑わしいファイルを Microsoft に送信する

![電子メール送信の例](../media/submission-file-flyout.PNG)

1. ファイルを送信するには、ポップアップ**からファイルを選択し**、スキャンしたいファイルをアップロードします。

2. [**送信**] ボタンをクリックします。

## <a name="related-topics"></a>関連項目

[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)

[Office 365 で脅威から保護する](protect-against-threats.md)

[Office 365 Advanced Threat Protection のレポートを表示する](view-reports-for-atp.md)
