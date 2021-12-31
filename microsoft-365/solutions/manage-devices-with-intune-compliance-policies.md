---
title: 手順 3. Intune を搭載したデバイスのコンプライアンス ポリシーを設定する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
description: デバイスが環境にアクセスするための最小要件を指定するデバイス コンプライアンス ポリシーを作成する方法を学びます。
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- Create compliance policies
- Intune device compliance policy
ms.custom: ''
keywords: ''
ms.openlocfilehash: 46507c17562c7f7d60363d931fccadc6a67683f1
ms.sourcegitcommit: 36a19d80fe3f053df0fec398a7ff2dfc777f9730
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/30/2021
ms.locfileid: "61645874"
---
# <a name="step-3-set-up-compliance-policies-for-devices-with-intune"></a>手順 3. Intune を搭載したデバイスのコンプライアンス ポリシーを設定する

デバイスを管理に登録すると、環境内のデータのセキュリティと制御をさらに強化できます。 「[手順2. デバイスを管理に登録する](manage-devices-with-intune-enroll.md)」では、Intune とオートパイロットを使用してこれを実現する方法について詳しく説明します。 この記事では、デバイス コンプライアンス ポリシーを構成する次の手順について説明します。 

![デバイスを管理する手順](../media/devices/intune-mdm-step-2.png#lightbox)

アプリやデータにアクセスしているデバイスが最小要件を満たしていることを確認する必要があります。たとえば、デバイスがパスワードまたは PIN で保護されており、オペレーティング システムが最新であることです。 コンプライアンス ポリシーは、デバイスが満たす必要のある要件を定義する方法です。 MEM は、これらのコンプライアンス ポリシーを使用して、デバイスを準拠または非準拠としてマークします。このバイナリ状態は Azure AD に渡され、条件付きアクセス ルールでこの状態を使用して、デバイスによるリソースへのアクセスを許可または禁止できます。 

## <a name="configuring-device-compliance-policies"></a>デバイス コンプライアンス ポリシーの構成

このガイダンスは、推奨される[ゼロ トラスト ID およびデバイス アクセス ポリシー](../security/office-365-security/microsoft-365-policies-configurations.md)と緊密に連携しています。

この図は、コンプライアンス ポリシーを定義する作業が、ゼロ トラストが推奨するポリシー セット全体のどこに当てはまるかを示しています。 

[![ゼロトラスト ID とデバイス アクセス ポリシー](../media/devices/identity-device-define-compliance.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-define-compliance.png)

この図では、デバイス コンプライアンス ポリシーの定義は、ゼロ トラスト フレームワーク内で推奨レベルの保護を実現するための依存関係です。 

デバイス コンプライアンス ポリシーを構成するには、[ゼロトラスト ID およびデバイス アクセス ポリシー](../security/office-365-security/microsoft-365-policies-configurations.md)に規定されている推奨ガイダンスと設定を使用します。 次の表は、各プラットフォームの推奨設定を含む、Intune でこれらのポリシーを構成するための手順に直接リンクしています。


|ポリシー |詳細情報  |ライセンス |
|---------|---------|---------|
|[デバイス コンプライアンス ポリシーの定義](../security/office-365-security/identity-access-policies.md#define-device-compliance-policies)   |  プラットフォームごとに 1 つのポリシー       |  Microsoft 365 E3 または E5       |
|  |         |         |

## <a name="next-steps"></a>次の手順

Azure AD で条件付きアクセス ルールを作成する方法については、「[手順 4. 正常で準拠したデバイスを要求する](manage-devices-with-intune-require-compliance.md)」に進んでください。