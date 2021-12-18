---
title: 手順 4. Intune で正常で準拠しているデバイスを要求する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
ms.custom: ''
keywords: ''
description: ''
ms.openlocfilehash: b498e2e7698a4799559f9d681a6c3346d4e37672
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2021
ms.locfileid: "61302304"
---
# <a name="step-4-require-healthy-and-compliant-devices-with-intune"></a>手順 4. Intune で正常で準拠しているデバイスを要求する

条件付きアクセスは、サービスへのアクセスを許可する前に、デバイスの状態の追加の検証を提供します。 条件を指定しない限り、条件付きアクセスは機能しません。 [手順 3で.コンプライアンス ポリシーを設定](manage-devices-with-intune-compliance-policies.md)し、環境にアクセスするためにデバイスが満たす必要がある最小要件を指定するコンプライアンス ポリシーを定義しました。 この記事では、準拠しているデバイスを要求するために、Azure ADで対応する条件付きアクセス ポリシーを作成します。 これにより、企業のデータを安全に保ちながら、ユーザーは任意のデバイスから、任意の場所から作業できます。

デバイス コンプライアンス ポリシーを設定し、ユーザー グループに割り当てると、Intune では、デバイスAzure AD準拠しているかどうかが確認できます。 この状態をアクセスの条件として使用するには、Azure AD 管理者と一緒に条件付きアクセス ルールを作成して、準拠している PC とモバイル デバイスを要求する必要があります。


![デバイスを管理するための手順](../media/devices/intune-mdm-step-3.png#lightbox)

推奨されるゼロトラスト ID とデバイス アクセス ルール セットには、このルールが含まれます。 以下に 示す「[準拠している PC とモバイル デバイスの要求](../security/office-365-security/identity-access-policies.md#require-compliant-pcs-and-mobile-devices)」を参照してください。


[![ゼロトラスト ID とデバイス アクセス ポリシー](../media/devices/identity-device-require-compliance.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-require-compliance.png)



必ず次の手順を実行してください。
- コンプライアンス ポリシーに割り当てたユーザー グループと、条件付きアクセス ポリシーに割り当てられたユーザー グループを調整します。
- 条件付きアクセス ポリシーを完全に割り当てる前に、What If および 監査 Mode 機能を使用して条件付きアクセス ポリシーをテストします。 これは、ポリシーの結果を理解するのに役立ちます。
- アクセスするデータやアプリの機密性に合わせて猶予期間を設定します。 
- コンプライアンス ポリシーが規制や他のコンプライアンス要件に干渉しないようにします。 
- コンプライアンス ポリシーのデバイス チェックイン間隔について理解します。
- コンプライアンス ポリシーと構成プロファイルの間の競合を回避します。 選択した場合の結果を理解します。

ポリシー間の競合を含む Intune のデバイス プロファイルのトラブルシューティングについては、「[Microsoft Intuneのデバイス ポリシーとプロファイルに関する一般的な質問と回答](/mem/intune/configuration/device-profile-troubleshoot)」を参照してください。

注: 準拠している PC を要求し、モバイル デバイスを必要としない場合は、「[準拠している PC を必要とする (ただし、電話やタブレットは必須ではない)](../security/office-365-security/identity-access-policies.md)」を参照してください。 

## <a name="next-steps"></a>次の手順

手順 [5 に進みます。Microsoft Intune](manage-devices-with-intune-configuration-profiles.md)でデバイス プロファイルを展開する