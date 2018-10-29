---
author: meganbradley
ms.author: mbradley
ms.openlocfilehash: fa048980afcf3c50f7d990f9c88064df6ee5ebb5
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084424"
---
# <a name="docs-pr-validation-service"></a><span data-ttu-id="1e98e-101">Serviço de validação Docs PR</span><span class="sxs-lookup"><span data-stu-id="1e98e-101">Docs PR validation service</span></span>

<span data-ttu-id="1e98e-102">O serviço de validação Docs PR é um aplicativo do GitHub que executa regras de validação em arquivos em um PR.</span><span class="sxs-lookup"><span data-stu-id="1e98e-102">The Docs PR validation service is a GitHub app that runs validation rules on the files in a PR.</span></span>

<span data-ttu-id="1e98e-103">Quando o serviço de validação estiver habilitado em um repositório, o seguinte comportamento ocorrerá:</span><span class="sxs-lookup"><span data-stu-id="1e98e-103">When the validation service is enabled on a repo, you'll see the following behavior:</span></span>

1. <span data-ttu-id="1e98e-104">Você envia um PR.</span><span class="sxs-lookup"><span data-stu-id="1e98e-104">You submit a PR.</span></span>
1. <span data-ttu-id="1e98e-105">No comentário do GitHub que indica o status do PR, você verá o status de "verificações" habilitado no repositório.</span><span class="sxs-lookup"><span data-stu-id="1e98e-105">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repo.</span></span> <span data-ttu-id="1e98e-106">Neste exemplo, há duas verificações habilitadas, "Confirmar Validação" e "OpenPublishing.Build":</span><span class="sxs-lookup"><span data-stu-id="1e98e-106">Note that in this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![algumas verificações falharam](media/validation-failed.png)

   <span data-ttu-id="1e98e-108">O build poderá passar mesmo se a confirmação da validação falhar.</span><span class="sxs-lookup"><span data-stu-id="1e98e-108">Build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="1e98e-109">Clique em **Detalhes** para saber mais.</span><span class="sxs-lookup"><span data-stu-id="1e98e-109">Click **Details** for more information.</span></span>
1. <span data-ttu-id="1e98e-110">Na página Detalhes, você verá todas as verificações de validação que falharam, com informações sobre como corrigir os problemas:</span><span class="sxs-lookup"><span data-stu-id="1e98e-110">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues:</span></span>

   ![mensagem de validação](media/validation-details.png)

<span data-ttu-id="1e98e-112">Confira o sumário à esquerda deste artigo para ver a lista de validações do serviço no momento.</span><span class="sxs-lookup"><span data-stu-id="1e98e-112">See the left-hand TOC of this article for the list of validations currently in the service.</span></span>