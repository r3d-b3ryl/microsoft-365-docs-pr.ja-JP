---
title: 外部メール転送の構成と制御、自動転送、5.7.520 アクセス拒否、外部転送の無効化、管理者が外部転送を無効にした、送信スパム対策ポリシー
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 88c3dae4f5a6786fe4eddea0d5e1c61dda837a87
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080115"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Office 365 で外部電子メール転送を構成する

外部転送は、発信の*スパム対策ポリシー*によって制御され、構成された設定に基づいてユーザーのスコープを設定します。 現在、3つの設定がサポートされています。

- **Automatic** -このモードでは、転送されたメッセージが許可されているかどうかをシステムが判断します。  これは既定のモードで、このモードでは、システムによって自動的に外部転送がブロックされます。

- **オン**-自動外部転送が許可されていて、制限されていません。

- **Off** -自動外部転送が無効になり、エンドユーザーに配信不能レポート (NDR) が生成されます。

これらの設定を構成する方法の詳細については、「 [EOP で送信スパムフィルターを構成](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide)する」を参照してください。

## <a name="controlling-external-email-forwarding"></a>外部メール転送を制御する

組織の管理者として、組織外の受信トレイルールまたは SMTP 転送を使用して電子メールを自動的に転送できるユーザーを制限または制御するには、会社の要件があります。 メールの転送は便利な機能ですが、組織またはパートナーを攻撃するために利用できる攻撃者に情報を提供することによっても、情報の漏洩によってリスクが生じる可能性があります。

Office 365 では、受信トレイルールまたはメールボックス構成のいずれかを使用した自動の外部転送を許可しません。これは、セキュリティで保護された既定のポリシーです。 ただし、管理者は組織内のすべてのユーザーまたは一部のユーザーについてこれらの設定を変更できます。 内部ユーザー間でのメッセージ転送は、このような変更による影響を受けません。

> [!NOTE]
> Office 365 で外部アドレスへの自動転送を無効にすると、[メッセージセンター](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter)の投稿によって伝達された詳細をフェーズ内でロールアウトすることができます。 管理者がこれらの変更を準備するには、事前にポリシーを変更して、ユーザーに混乱が発生しないようにする必要があります。

組織内の自動転送 (受信トレイルールまたは SMTP 転送) を使用しているユーザーの詳細については、「[自動転送](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide)されたメッセージ」レポートを参照してください。

## <a name="the-blocked-email-forwarding-message"></a>ブロックされたメール転送メッセージ

メッセージが自動的に転送されると検出され、組織*のポリシーに*よって**配信不能レポート (NDR)** がエンドユーザーに返されます。 レポートには、メッセージが配信されなかったことが示されます。 NDR の形式は次のとおりです。 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
