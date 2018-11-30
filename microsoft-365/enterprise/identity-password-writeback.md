---
title: '手順 9: パスワードの更新を簡素化する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: ハイブリッド環境でのパスワードの書き戻しについて理解し、構成します。
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869181"
---
# <a name="step-9-simplify-password-updates"></a>手順 9: パスワードの更新を簡素化する

*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

この手順では、ユーザーが Azure Active Directory (AD) からパスワードをリセットできるようにします。リセットされたパスワードはローカル Windows Server Active Directory (AD) にレプリケートされます。これは、パスワードの書き戻しと呼ばれます。パスワードの書き戻しにより、ユーザーはユーザー アカウントとその属性が保存されているオンプレミス Windows Server AD でパスワードを更新する必要がなくなります。これは、オンプレミス ネットワークにリモート アクセス接続できないローミング ユーザーやリモート ユーザーにとって役立ちます。

パスワードの書き戻しは、Identity Protection 機能 (アカウント侵害が発生する可能性が高い危険が検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。

その他の情報と構成手順については、「[Azure AD SSPR とパスワード書き戻し](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)」を参照してください。

>[!Note]
>最適なエクスペリエンスとリリースされた新機能を利用できるようにするため、Azure AD Connect の最新バージョンにアップグレードします。詳細については、「[Azure AD Connect のカスタム インストール](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)」を参照してください。
>

中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-pw-writeback)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [ユーザー サインインを簡素化する](identity-single-sign-on.md) |

