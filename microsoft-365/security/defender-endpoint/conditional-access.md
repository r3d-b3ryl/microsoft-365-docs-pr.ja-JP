---
title: 条件付きアクセスを有効にして、ユーザー、デバイス、およびデータをより良く保護する
description: 条件付きアクセスを有効にして、デバイスが危険にさらされているとみなされ、アプリケーションが非準拠であると判断された場合にアプリケーションが実行されるのを防ぐ。
keywords: 条件付きアクセス、ブロック アプリケーション、セキュリティ レベル、Intune、
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ae325d2d6c776c41ef12164ba48da9240e0e628b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59163742"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>条件付きアクセスを有効にして、ユーザー、デバイス、およびデータをより良く保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

条件付きアクセスは、セキュリティで保護されたデバイスだけがアプリケーションにアクセスし、ユーザーとエンタープライズ情報をより適切に保護するのに役立つ機能です。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4byD1]

条件付きアクセスを使用すると、デバイスのリスク レベルに基づいてエンタープライズ情報へのアクセスを制御できます。 これにより、信頼できるアプリケーションを使用して信頼できるデバイス上の信頼できるユーザーを維持できます。

ポリシーを適用して、デバイスが準拠状態に戻るまでアプリケーションの実行を停止することで、デバイスとアプリケーションがネットワークから情報を実行およびアクセスできるセキュリティ条件を定義できます。

Defender for Endpoint での条件付きアクセスの実装は、Microsoft Intune (Intune) デバイス コンプライアンス ポリシーと Azure Active Directory (Azure AD) 条件付きアクセス ポリシーに基づいて行います。

コンプライアンス ポリシーは、条件付きアクセスと一緒に使用して、1 つ以上のデバイス コンプライアンス ポリシー ルールを満たすデバイスだけがアプリケーションにアクセスできます。

## <a name="understand-the-conditional-access-flow"></a>条件付きアクセス フローについて

条件付きアクセスが実行され、デバイスで脅威が見られると、脅威が修復されるまで機密コンテンツへのアクセスがブロックされます。

フローは、デバイスのリスクが低、中、または高く見られるから始まります。 その後、これらのリスク判定が Intune に送信されます。

Intune でポリシーを構成する方法に応じて、条件付きアクセスを設定して、特定の条件が満たされるとポリシーが適用されます。

たとえば、リスクが高いデバイスに条件付きアクセスを適用する Intune を構成できます。

Intune では、デバイス コンプライアンス ポリシーが Azure AD条件付きアクセスと組み合わせて使用して、アプリケーションへのアクセスをブロックします。 並行して、自動調査と修復プロセスが開始されます。

 自動調査と修復が行なっている間も、ユーザーはデバイスを使用できますが、脅威が完全に修復されるまでエンタープライズ データへのアクセスはブロックされます。

デバイスで見つかったリスクを解決するには、デバイスを準拠した状態に戻す必要があります。 デバイスにリスクが見られない場合、デバイスは準拠状態に戻ります。

リスクに対処するには、次の 3 つの方法があります。

1. 手動または自動修復を使用します。
2. デバイスでアクティブなアラートを解決します。 これにより、デバイスからリスクが削除されます。
3. アクティブ なポリシーからデバイスを削除できます。そのため、条件付きアクセスはデバイスに適用されません。

手動による修復では、secops 管理者がアラートを調査し、デバイスで見られるリスクに対処する必要があります。 自動修復は、次のセクション「条件付きアクセスの構成」で提供される構成 [設定によって構成されます](configure-conditional-access.md)。

手動または自動修復によってリスクが削除されると、デバイスは準拠した状態に戻り、アプリケーションへのアクセスが許可されます。

次の一連のイベントの例では、条件付きアクセスの動作について説明します。

1. ユーザーが悪意のあるファイルを開き、Defender for Endpoint はデバイスにリスクの高いフラグを設定します。
2. 高リスク評価は Intune に渡されます。 並行して、特定された脅威を修復するために自動調査が開始されます。 また、特定された脅威を修復するために手動で修復することもできます。
3. Intune で作成されたポリシーに基づいて、デバイスは準拠していないとマークされます。 その後、評価は Intune 条件付きアクセス ADによって Azure サーバーに伝達されます。 Azure ADでは、対応するポリシーが適用され、アプリケーションへのアクセスがブロックされます。
4. 手動または自動化された調査と修復が完了し、脅威が削除されます。 Defender for Endpoint では、デバイスにリスクがないと見なされ、Intune はデバイスが準拠状態にあると評価します。 Azure ADアプリケーションへのアクセスを許可するポリシーを適用します。
5. これで、ユーザーはアプリケーションにアクセスできます。

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Endpoint で条件付きアクセスを構成する](configure-conditional-access.md)
