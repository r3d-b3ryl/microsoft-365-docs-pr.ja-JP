---
title: チュートリアル-スプーフィングインテリジェンスの洞察
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理者は、スプーフィングインテリジェンスの理解がどのように機能するかを知ることができます。 電子メール認証の確認 (SPF、DKIM、または DMARC) を通過しないドメインから組織に対して、どの送信者がメールを正当に送信しているかを迅速に判断できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920480"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>チュートリアル-Office 365 の Microsoft Defender のスプーフィングインテリジェンスの洞察

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Office 365 の Defender を使用する Microsoft 365 組織では、スプーフィングインテリジェンスの洞察を使用して、どの送信者が認証された電子メールを正当に送信しているかをすばやく判断できます (SPF、DKIM、または DMARC チェックに合格していないドメインからのメッセージ)。

既知の送信者が既知の場所からスプーフィングされたメッセージを送信することを許可することにより、誤検知 (正常なメールが不良としてマークされる) を減らすことができます。 許可された送信者を監視することで、安全でないメッセージが組織内に到着しないようにするためのセキュリティの追加の層を提供します。

レポートと分析情報の詳細については、「 [Security & コンプライアンスセンターのレポートと分析](reports-and-insights-in-security-and-compliance.md)」を参照してください。

このチュートリアルは、セキュリティ & コンプライアンスセンターに対していくつかの方法があります。 レポートと分析情報の移動については、「 [関連項目](#related-topics) 」セクションのチュートリアルを参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [ **Security dashboard** ] ページに直接移動するには、を使用 <https://protection.office.com/searchandinvestigation/dashboard> します。

  セキュリティ & コンプライアンスセンターでは、複数のダッシュボードからスプーフィングインテリジェンスの洞察を確認できます。 どのダッシュボードを使用しているかに関係なく、洞察は同じ情報を提供し、同じタスクをすばやく実行することができます。

- このトピックの手順を実行する前に、アクセス許可を割り当てる必要があります。 スプーフィングインテリジェンスの洞察を使用するには、次のいずれかの役割グループのメンバーである必要があります。

  - **組織の管理** または [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ管理者** 。
  - **組織の管理** または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **検疫管理** 。
  - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の **セキュリティ閲覧者** 。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の **表示限定の組織管理** 。

- Office 365 の Microsoft Defender で、フィッシング対策ポリシーのスプーフィングインテリジェンスを有効または無効にします。 詳細については、「 [Configure フィッシング対策ポリシーを Microsoft Defender の Office 365 に構成する](configure-atp-anti-phishing-policies.md)」を参照してください。

- スプーフィングインテリジェンスを使用して、認証されていないメッセージを送信する送信者を監視および管理する方法については、「 [Microsoft 365 でスプーフィングインテリジェンスを構成](learn-about-spoof-intelligence.md)する」を参照してください。

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターでのスプーフィングインテリジェンスに関する洞察を開く

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** ] ダッシュボードに移動し \> **ます。**

2. [ **Insights** ] 行で、次のいずれかのアイテムを探します。

   - **スプーフィングインテリジェンスが有効になっ** ています。この洞察は、 **過去30日間の認証に失敗したスプーフィングドメイン** と呼ばれます。 これが既定です。
   - **スプーフィングインテリジェンスが無効になっ** ています。名前付きの **スプーフィング保護を有効** にし、それをクリックすると、スプーフィングインテリジェンスを有効にすることができます。

3. ダッシュボードの洞察には、次のような情報が表示されます。

   ![スプーフィングインテリジェンスの洞察のスクリーンショット](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   この洞察には、次の2つのモードがあります。

   - [ **洞察モード** ]: スプーフィングインテリジェンスが有効になっている場合、過去30日間のスプーフィングインテリジェンス機能によって影響を受けたメッセージの数が洞察に表示されます。

   - **If モード** : スプーフィングインテリジェンスが無効な場合、過去30日間のスプーフィングインテリジェンス機能によって影響を受け *たメッセージの数が洞察* に表示されます。

   どちらの方法でも、洞察に表示される偽装されたドメインは、 **疑わしいドメイン** の組と **不審でないドメインのペア** という2つのカテゴリに分かれています。 これらのカテゴリは、確認のために3つの異なるバケットにさらに細分化されています。

   **ドメインペア** は、From アドレスと送信元インフラストラクチャの組み合わせです。

   - From アドレスは、電子メールクライアントの [差出人] ボックスに表示される送信者の電子メールアドレスです。 このアドレスは、アドレスとも呼ばれ `5322.From` ます。

   - 送信元のインフラストラクチャまたは送信者は、送信元 IP アドレスの逆引き DNS 参照 (PTR レコード) の組織ドメインです。 送信元の IP アドレスに PTR レコードがない場合、送信元の IP アドレスは、CIDR 表記法 (/24) で255.255.255.0 サブネットマスクを使用して識別されます。 たとえば、IP アドレスが192.168.100.100 の場合、送信者の完全な IP アドレスは 192.168.100.100/24 です。

   **疑わしいドメインペア** は次のとおりです。

   - **信頼度の高いスプーフィング** : 過去の送信パターンとドメインの評価スコアに基づいて、ドメインがスプーフィングされており、これらのドメインからのメッセージが悪意を持っている可能性が高いことを確信しています。

   - **適度な信頼度のスプーフィング** : 過去の送信パターンとドメインの評価スコアに基づいて、ドメインがスプーフィングされており、これらのドメインから送信されたメッセージが正当であると確信しています。 誤検知は、信頼度の高いスプーフィングよりも、このカテゴリの可能性が高くなります。

   - **不審でないドメインのペア** ( **rescued スプーフィング** を含む): ドメインに障害が発生した明示的な電子メール認証チェック [SPF](how-office-365-uses-spf-to-prevent-spoofing.md)、 [dkim](use-dkim-to-validate-outbound-email.md)、および [DMARC](use-dmarc-to-validate-email.md))。 しかし、ドメインは暗黙的な電子メール認証チェック ([複合認証](email-validation-and-authentication.md#composite-authentication)) に合格しています。 その結果、メッセージに対してスプーフィング対策アクションが実行されませんでした。

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>スプーフィングインテリジェンスの洞察から、疑わしいドメインペアに関する詳細情報を表示する

1. スプーフィングインテリジェンスの洞察で、いずれかのドメインペア (high、中、または rescued) をクリックします。

   [ **スプーフィングインテリジェンスの理解** ] ページが表示されます。 このページには、認証されていない電子メールを組織に送信している送信者の一覧が表示されます。

   この情報は、スプーフィングされたメッセージを承認するか、さらにアクションを実行する必要があるかを判断するのに役に立ちます。

   メッセージ数、スプーフィングが最後に検出された日付などによって、情報を並べ替えることができます。

2. テーブル内のアイテムを選択して、ドメインペアに関する豊富な情報を含む詳細ウィンドウを開きます。 情報には次のものが含まれます。
   - これをキャッチした理由。
   - 必要な作業
   - ドメインの概要。
   - 送信者に関する WhoIs データ。
   - 同じ送信者からのテナントに表示された同様のメッセージ。

   ここから、ドメインペアを **Allowedtospoof** safe sender リストから追加または削除することもできます。

   ![スプーフィングインテリジェンスの詳細情報ウィンドウにあるドメインのスクリーンショット](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a>AllowedToSpoof リストのドメインを追加または削除する

ドメインのペアのスプーフィングインテリジェンスに関する情報ウィンドウにある、AllowedToSpoof (安全な送信者) 一覧のドメインを追加または削除します。 それに応じてトグルを設定するだけです。

ドメインペアを許可すると、偽装されたドメイン *と* 送信元インフラストラクチャの組み合わせのみが許可されます。 偽装されたドメインからの電子メールを任意のソースから許可することも、すべてのドメインの送信元インフラストラクチャから電子メールを許可することもできません。

たとえば、次のドメインペアが組織にスプーフィングされたメッセージを送信することを許可します。

- *スプーフィング* されたドメイン: gmail.com "
- *インフラストラクチャの送信* `tms.mx.com` :

そのドメインペアからの電子メールのみがスプーフィングを許可されます。 他の送信者が gmail.com をスプーフィングすることは許可されていません。 Tms.mx.com からの他のドメイン内のメッセージは、スプーフィングインテリジェンスによってチェックされます。

## <a name="related-topics"></a>関連項目

[Microsoft 365 でのスプーフィング対策保護](anti-spoofing-protection.md)
