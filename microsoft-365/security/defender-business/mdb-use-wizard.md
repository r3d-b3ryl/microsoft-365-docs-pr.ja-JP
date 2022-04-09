---
title: Microsoft Defender for Businessでセットアップ ウィザードを使用する
description: Defender for Business には、ウィザードに似たセットアップと構成プロセスが含まれています。 ウィザードを使用して、時間と労力を節約します。
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 04/08/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.custom: intro-get-started
ms.openlocfilehash: ad070273567d350973037f1ac5a0192036d22187
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2022
ms.locfileid: "64746647"
---
# <a name="use-the-setup-wizard-in-microsoft-defender-for-business"></a>Microsoft Defender for Businessでセットアップ ウィザードを使用する

> [!IMPORTANT]
> Microsoft Defender for Businessは、2022 年 3 月 1 日以降、[Microsoft 365 Business Premium](../../business-premium/index.md)のお客様に展開されます。 スタンドアロン サブスクリプションとしての Defender for Business はプレビュー段階にあり、 [ここにサインアップ](https://aka.ms/mdb-preview) して要求する顧客と IT パートナーに段階的にロールアウトされます。 プレビューには [シナリオの初期セット](mdb-tutorials.md#try-these-preview-scenarios)が含まれており、定期的に機能を追加します。
> 
> この記事の一部の情報は、市販される前に大幅に変更される可能性があるプレリリースされた製品/サービスに関連しています。 Microsoft は、ここに記載されている情報に対して、明示的または黙示的な保証を行いません。 

Microsoft Defender for Businessは、初期セットアップと構成のためのウィザードのようなエクスペリエンスを使用して、中小企業の時間と労力を節約するように設計されました。 セットアップ ウィザードでは、セキュリティ チームへのアクセス許可の付与、セキュリティ チームの電子メール通知の設定、会社のWindows デバイスのオンボードを行います。

:::image type="content" source="media/mdb-wizard-start.png" alt-text="Defender for Business を設定するためのウィザードのホーム画面のスクリーンショット。":::

>
> **少し時間ありますか?**
> <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Businessに関する短いアンケート</a>を受けてください。 ご意見をお寄せください。
>

## <a name="overview-of-the-setup-wizard"></a>セットアップ ウィザードの概要

> [!IMPORTANT]
> 開始する前に、Microsoft 365 サブスクリプションにユーザーが既に追加されていることを確認します。 このタスクのヘルプについては、「ユーザーの [追加とライセンスの割り当てを同時に](../../admin/add-users/add-users.md)行う」を参照してください。

このウィザードは、Defender for Business を迅速かつ効率的に設定および構成するのに役立ちます。 ウィザードでは、次の手順を実行します。

1. **ユーザーのアクセス許可を割り当てます**。 この手順では、セキュリティ チームにMicrosoft 365 Defender ポータル ()[https://security.microsoft.com](https://security.microsoft.com) へのアクセス権を付与します。 このポータルでは、お客様とセキュリティ チームがセキュリティ機能を管理し、アラートを表示し、検出された脅威に対して必要なアクションを実行します。 ポータルへのアクセスは、特定のアクセス許可を意味するロールを通じて付与されます。

   Defender for Business では、セキュリティ チームのメンバーに次の 3 つのロールのいずれかを割り当てることができます。<br/>
   
      - **グローバル管理者**: グローバル管理者は、Microsoft 365 テナント全体のすべての設定を表示および編集できます。 グローバル管理者は、会社のMicrosoft 365 サブスクリプションの初期セットアップと構成を行います。 
      - **セキュリティ管理者**: セキュリティ管理者は、セキュリティ設定を表示および編集し、脅威が検出されたときにアクションを実行できます。
      - **セキュリティ リーダー**: セキュリティ リーダーはレポート内の情報を表示できますが、セキュリティ設定を変更することはできません。 
      
      [ロールとアクセス許可の詳細については、こちらを参照してください](mdb-roles-permissions.md)。 

2. **電子メール通知を設定します**。 この手順では、セキュリティ チームの電子メール通知を設定できます。 その後、アラートが生成されたとき、または新しい脆弱性が検出された場合、セキュリティ チームは、自分のデスクから離れている場合でも、そのアラートについて取り上げません。 

   [電子メール通知の詳細については、こちらを参照してください](mdb-email-notifications.md)。 

3. **Windowsデバイスをオンボードして構成します**。 この手順では、会社のWindows デバイスを Defender for Business にすばやくオンボードできます。 デバイスをすぐにオンボードすると、初日からデバイスを保護できます。 

   - Microsoft エンドポイント マネージャー (Microsoft Intuneを含む) を **既に使用していて**、会社にデバイスがエンドポイント マネージャーに登録されている場合は、登録済みのWindows デバイスの一部または全部に [対して自動オンボードを](mdb-onboard-devices.md#automatic-onboarding-for-windows-devices-enrolled-in-microsoft-endpoint-manager)使用するかどうかを確認するメッセージが表示されます。 自動オンボードでは、エンドポイント マネージャーと Defender for Business の間の接続が設定され、Windowsデバイスが Defender for Business にシームレスにオンボードされます。 
   - **エンドポイント マネージャーをまだ使用していない場合は**、[ローカル スクリプトを使用してデバイスを Defender for Business にオンボード](mdb-onboard-devices.md#local-script-in-defender-for-business)できます。 
   
   [Microsoft Defender for Businessへのデバイスのオンボードの詳細については、「」を参照してください](mdb-onboard-devices.md)。
   
4. **セキュリティ ポリシーを構成します**。 Defender for Business には、会社のデバイスに適用できる次世代の保護とファイアウォール保護の既定のセキュリティ ポリシーが含まれています。 これらの既定のポリシーでは、推奨される設定が使用され、デバイスに強力な保護を提供するように設計されています。 独自のセキュリティ ポリシーを作成することもできます。 また、既にエンドポイント マネージャーを使用している場合は、引き続きこれを使用してセキュリティ ポリシーを管理できます。

   詳細については、「 [セキュリティ ポリシーと設定の表示と編集](mdb-configure-security-settings.md)」を参照してください。 |

## <a name="what-happens-if-i-dont-use-the-wizard"></a>ウィザードを使用しない場合はどうなりますか?

セットアップ ウィザードの使用は省略可能です。 ウィザードを使用しないことを選択した場合、またはセットアップ プロセスが完了する前にウィザードが閉じられる場合は、自分でセットアップと構成プロセスを完了できます。 これらの手順については、「[Microsoft Defender for Businessのセットアップと構成](mdb-setup-configuration.md)」を参照してください。

1. セキュリティ チームが Microsoft 365 Defender ポータル ()[https://security.microsoft.com](https://security.microsoft.com) にアクセスして使用できるように **[、ロールとアクセス許可を割り当てます](mdb-roles-permissions.md)**。

2. 新しいアラートや脆弱性に関するループに入るように **[、セキュリティ チームの電子メール通知を設定](mdb-email-notifications.md)** します。

3. **[Defender](mdb-onboard-devices.md)** for Business によって保護されるようにデバイスをオンボードします。

4. 次世代の保護、ファイアウォール保護、Web コンテンツ のフィルター処理など、**[セキュリティ ポリシーを管理](mdb-configure-security-settings.md)** します。

## <a name="next-steps"></a>次のステップ

- [セキュリティ チームの電子メール通知を設定する](mdb-email-notifications.md)

- [Microsoft 365 Defender ポータルを使用した概要](mdb-get-started.md)

- [脅威&脆弱性管理ダッシュボードを使用する](mdb-view-tvm-dashboard.md)