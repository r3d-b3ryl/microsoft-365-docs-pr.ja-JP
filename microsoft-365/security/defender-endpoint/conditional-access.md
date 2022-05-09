---
title: 条件付きアクセスを有効にして、ユーザー、デバイス、データをより適切に保護する
description: 条件付きアクセスを有効にして、デバイスが危険にさらされていると見なされ、アプリケーションが非準拠であると判断された場合にアプリケーションが実行されないようにします。
keywords: 条件付きアクセス, アプリケーションのブロック, セキュリティ レベル, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8ee1b1542eb2e737da509ce12ad9c2a605a4ffa5
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2021
ms.locfileid: "61170552"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>条件付きアクセスを有効にして、ユーザー、デバイス、データをより適切に保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

条件付きアクセスは、セキュリティで保護されたデバイスのみがアプリケーションにアクセスできるようにすることで、ユーザーと企業情報をより適切に保護するのに役立つ機能です。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4byD1]

条件付きアクセスを使用すると、デバイスのリスク レベルに基づいてエンタープライズ情報へのアクセスを制御できます。 これにより、信頼されたアプリケーションを使用して信頼できるデバイスで信頼されたユーザーを維持できます。

デバイスとアプリケーションを実行し、デバイスが準拠状態に戻るまでアプリケーションの実行を停止するポリシーを適用することで、ネットワークから情報にアクセスできるセキュリティ条件を定義できます。

Defender for Endpoint での条件付きアクセスの実装は、Microsoft Intune (Intune) デバイス コンプライアンス ポリシーとAzure Active Directory (Azure AD) 条件付きアクセス ポリシーに基づいています。

コンプライアンス ポリシーは条件付きアクセスと共に使用され、1 つ以上のデバイス コンプライアンス ポリシー規則を満たすデバイスのみがアプリケーションにアクセスできるようにします。

## <a name="understand-the-conditional-access-flow"></a>条件付きアクセス フローを理解する

条件付きアクセスは、デバイスで脅威が見られると、脅威が修復されるまで機密コンテンツへのアクセスがブロックされるように配置されます。

フローは、デバイスのリスクが低、中、または高と見なされることから始まります。 これらのリスク決定は、Intuneに送信されます。

Intuneでポリシーを構成する方法に応じて、特定の条件が満たされたときにポリシーが適用されるように条件付きアクセスを設定できます。

たとえば、リスクの高いデバイスに条件付きアクセスを適用するようにIntuneを構成できます。

Intuneでは、デバイス コンプライアンス ポリシーがAzure AD条件付きアクセスと組み合わせて使用され、アプリケーションへのアクセスがブロックされます。 並行して、自動調査と修復プロセスが開始されます。

 自動調査と修復が行われている間、ユーザーはデバイスを引き続き使用できますが、脅威が完全に修復されるまで、エンタープライズ データへのアクセスはブロックされます。

デバイスで見つかったリスクを解決するには、デバイスを準拠状態に戻す必要があります。 デバイスにリスクが見つからない場合、デバイスは準拠状態に戻ります。

リスクに対処するには、次の 3 つの方法があります。

1. 手動または自動修復を使用します。
2. デバイス上のアクティブなアラートを解決します。 これにより、デバイスからリスクが削除されます。
3. アクティブなポリシーからデバイスを削除できるため、条件付きアクセスはデバイスに適用されません。

手動修復では、secops 管理者がアラートを調査し、デバイスで見られるリスクに対処する必要があります。 自動修復は、次のセクション「 [条件付きアクセス](configure-conditional-access.md)の構成」で提供される構成設定を使用して構成されます。

手動または自動修復によってリスクが削除されると、デバイスは準拠状態に戻り、アプリケーションへのアクセスが許可されます。

次の一連のイベントの例では、条件付きアクセスの動作について説明します。

1. ユーザーが悪意のあるファイルを開き、Defender for Endpoint によってデバイスに高リスクのフラグが設定されます。
2. リスクの高い評価はIntuneに渡されます。 同時に、特定された脅威を修復するために自動調査が開始されます。 手動修復を実行して、特定された脅威を修復することもできます。
3. Intuneで作成されたポリシーに基づいて、デバイスは非準拠としてマークされます。 その後、評価はIntune条件付きアクセス ポリシーによってAzure ADに伝達されます。 Azure ADでは、アプリケーションへのアクセスをブロックするために、対応するポリシーが適用されます。
4. 手動または自動の調査と修復が完了し、脅威が削除されます。 Defender for Endpoint は、デバイスにリスクがないことを確認し、Intuneデバイスが準拠状態であることを評価します。 Azure ADアプリケーションへのアクセスを許可するポリシーを適用します。
5. ユーザーはアプリケーションにアクセスできるようになりました。

## <a name="related-topic"></a>関連トピック

- [Microsoft Defender for Endpointで条件付きアクセスを構成する](configure-conditional-access.md)
