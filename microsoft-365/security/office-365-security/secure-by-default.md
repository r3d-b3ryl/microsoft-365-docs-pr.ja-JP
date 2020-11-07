---
title: Office 365 で既定でセキュリティ保護されている
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 組織の電子メールセキュリティレポートを検索して使用する方法について説明します。 電子メールセキュリティレポートは、セキュリティ & コンプライアンスセンターで利用できます。
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944479"
---
# <a name="secure-by-default-in-office-365"></a>Office 365 で既定でセキュリティ保護されている

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[既定でセキュリティ保護] は、可能な限り最も安全な既定の設定を定義するために使用される用語です。 

ただし、セキュリティは生産性にバランスをとる必要があります。 これには、次のようなバランスを含めることができます。
- 有用性: 設定は、ユーザーの生産性を向上させることはできません。
- リスク: セキュリティが重要なアクティビティをブロックする可能性があります。
- 従来の設定: 新しい高度な設定が改善された場合でも、以前の製品や機能のいくつかの構成は、ビジネス上の理由から維持する必要があります。 

Exchange Online のメールボックスを使用する Microsoft 365 組織は、Exchange Online Protection (EOP) によって保護されています。 この保護には次のものが含まれます。
1. 疑いのあるマルウェアを含む電子メールは自動的に検疫され、受信者に通知されます。 [EOP でマルウェア対策ポリシーを構成するを](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide)参照してください。
1. 「高信頼」として識別されたフィッシングメールは、スパム対策ポリシーアクションに従って処理されます。 [EOP の「スパム対策ポリシーの構成」を](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide)参照してください。

Microsoft は、お客様に既定でセキュリティを維持することを目的としているため、一部のテナントは、マルウェアや高信頼フィッシングには適用されません。 これらのオーバーライドは次のとおりです。
- 許可された送信者リストまたは許可されたドメインリスト (スパム対策ポリシー)
- Outlook の差出人セーフリスト
- IP 許可一覧 (接続フィルター)

これらのオーバーライドの詳細については、「 [安全な送信者リストを作成](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365)する」を参照してください。

セキュリティで保護されている既定の設定は、有効または無効にすることはできませんが、潜在的な危険または不要なメッセージをメールボックスから保持するためのボックスからフィルターを適用する方法を示しています。 マルウェアと信頼度の高いフィッシングを検疫に送信する必要があります。 マルウェアまたは信頼度の高いフィッシングとして検疫されたメッセージを管理できるのは管理者のみです。また、そこから Microsoft に誤検知を報告することもできます。 詳細については、「 [EOP で管理者として検疫済みメッセージおよびファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

## <a name="exceptions"></a>例外
すべてのフィルターをバイパスする唯一のオーバーライドは次のとおりです。
- Exchange トランスポートルール (ETR)/メールフロールール。  メールフロールールを使用して、EOP のメッセージでスパム信頼レベル (SCL) を設定します。
- テナントの許可/ブロックリスト: テナントの許可/ブロックリスト内の Url とファイルを管理します。


これらの種類のオーバーライドは、次のような場合に役立ちます。
- フィッシングのシミュレーション: シミュレートされた攻撃は、実際の攻撃が組織に影響を与える前に、脆弱性のあるユーザーを特定するのに役立ちます。
- セキュリティ/SecOps メールボックス: セキュリティチームがフィルター処理されていないメッセージを取得するために使用する専用のメールボックス (良好および不良)。 チームは、悪意のあるコンテンツが含まれているかどうかを確認することができます。
- サードパーティのフィルター: サードパーティ製のフィルターがメールフィルターを管理するために、サードパーティベンダーの中には EOP (SCL =-1) をオフにすることをお勧めします。  Microsoft では、EOP をオフにすることは推奨されていません。 EOP は、Defender for Office 365 のために必要です。 
- 誤検知: Microsoft によってまだ分析されている特定のメッセージを [管理者の送信から](admin-submission.md)許可することができます。 すべてのオーバーライドと同様に、一時的なものにすることをお勧めします。
