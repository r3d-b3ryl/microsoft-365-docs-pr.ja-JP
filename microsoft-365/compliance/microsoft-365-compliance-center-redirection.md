---
title: セキュリティ/コンプライアンス センター Office 365コンプライアンス センターからコンプライアンス センターにユーザー Microsoft 365リダイレクトする
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: セキュリティ とコンプライアンス センターのOffice 365コンプライアンス センターに自動的にリダイレクトする方法Microsoft 365します。
ms.collection: M365-security-compliance
ms.openlocfilehash: b51b2e225c833ac499379bbee119f8cb6f4216e9
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782839"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a>セキュリティ/コンプライアンス センター Office 365コンプライアンス センターからコンプライアンス センターにユーザー Microsoft 365リダイレクトする

この記事では、Office 365 セキュリティ とコンプライアンス センター (protection.office.com) から Microsoft 365 コンプライアンス センター (compliance.microsoft.com) へのコンプライアンス ソリューションにアクセスするユーザーの自動リダイレクトのしくみについて説明します。

## <a name="what-to-expect"></a>想定される変化

自動リダイレクトは、セキュリティとコンプライアンス (Office 365) で次のコンプライアンス関連のソリューションにアクセスしているすべてのユーザーに対して既定 protection.office.com。

- データ損失防止 (DLP)
- 分類
- 情報ガバナンス
- レコード管理
- コミュニケーションコンプライアンス (以前は '監督')

ユーザーは、コンプライアンス センター (Microsoft 365) で同 compliance.microsoft.com。

>[!NOTE]
>Office 365 セキュリティとコンプライアンス センターに含まれる他のコンプライアンス ソリューションについては、Microsoft 365 コンプライアンス センターまたは Office 365 セキュリティ とコンプライアンス センターでこれらのソリューションを管理し続けます。 これらのコンプライアンス ソリューションの自動リダイレクトは、近日利用可能になります。*

この機能と関連付けられたコントロールでは、Microsoft Defender のセキュリティ機能の自動リダイレクトが有効Office 365。 セキュリティ機能のリダイレクトを有効にするには[、「Microsoft Defender](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection)からアカウントをリダイレクトする」を参照Office 365セキュリティ センター Microsoft 365を参照してください。

## <a name="can-i-go-back-to-using-the-former-portal"></a>以前のポータルを使用して戻ってみませんか?

何かが機能していない場合、または Microsoft 365 コンプライアンス センター ポータルで完了できない場合は、すべてのユーザーの自動リダイレクトを一時的に無効にできます。

>[!IMPORTANT]
>コンプライアンス Microsoft 365は、現在、セキュリティ/コンプライアンス センターで管理されているコンプライアンス ソリューションのOffice 365管理ポータルです。 すべてのMicrosoft 365ソリューションは、コンプライアンス センターでのみMicrosoft 365されます。 コンプライアンス センターへのリダイレクトMicrosoft 365無効にするには、短期的なソリューションを使用する必要があります。*

すべてのユーザーの Office 365 およびコンプライアンス センター (protection.microsoft.com) に切り替えるには、次の手順を実行します。

1. グローバル管理者として[、Microsoft 365](https://compliance.microsoft.com)コンプライアンス センターにサインインするか、Azure Active directory でコンプライアンス管理者のアクセス許可を持つ任意のアカウントを使用します。
2. コンプライアンス センターの **設定**  >  **に移動します**。
3. [自動リダイレクト] 設定を [オフ] に **切り替えます**。
4. メッセージが **表示されたら、[** オフにし、フィードバックを共有する] を選択します。

無効にすると、ユーザーは compliance.microsoft.com にルーティングされ、Office 365 セキュリティ とコンプライアンス センター (protection.microsoft.com) に protection.microsoft.com。 この設定は、グローバル管理者またはコンプライアンス管理者がいつでも再度有効にできます。

## <a name="related-information"></a>関連情報

- [Microsoft 365センターの概要](/microsoft-365/compliance/microsoft-365-compliance-center)
